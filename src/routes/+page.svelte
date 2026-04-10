<script lang="ts">
    // labels per section
    const sections = [
        { id: 'top-rated',      title: 'נבחרי הציבור המדורגים ביותר', subtitle: 'מיועדים לפרס השנה עבור פעילותם לטובת העם', label: 'נבחר ציבור', href: '/top-rated',      showImage: true,  showMedals: true  },
        { id: 'knesset',        title: 'דירוג חברי כנסת',              subtitle: '',                                            label: 'חבר כנסת',   href: '/knesset',        showImage: false, showMedals: true  },
        { id: 'judges',         title: 'דירוג שופטים',                  subtitle: '',                                            label: 'שופט',        href: '/judges',         showImage: false, showMedals: false },
        { id: 'public-servants',title: 'דירוג עובדי ציבור',             subtitle: '',                                            label: 'עובד ציבור',  href: '/public-servants',showImage: false, showMedals: false },
    ];
</script>

<div class="space-y-8 md:space-y-16 py-4 md:py-8">

    {#each sections as sec}
    <section>
        <div class="text-center mb-4 md:mb-8">
            {#if sec.showImage}
            <div class="flex justify-center mb-4 md:mb-6">
                <div class="relative inline-block">
                    <img
                        src="/images/public-rating.jpeg"
                        alt="דירוג ציבורי"
                        class="h-48 md:h-96 w-auto object-contain rounded-2xl md:rounded-3xl"
                    />
                    <div class="absolute inset-0 rounded-2xl md:rounded-3xl" style="box-shadow: inset 0 0 30px 10px #0f172a;"></div>
                </div>
            </div>
            {/if}
            <h2 class="text-2xl md:text-4xl font-black text-white mb-2 md:mb-3">{sec.title}</h2>
            {#if sec.subtitle}
            <p class="text-amber-400 text-sm md:text-lg font-bold">{sec.subtitle}</p>
            {/if}
        </div>

        <div class="bg-white/5 border border-white/10 rounded-2xl p-3 md:p-6">

            <!-- מובייל: פריסת פודיום -->
            <div class="flex flex-col items-center gap-4 md:hidden">
                <!-- שורה עליונה: #2 | #1 (גבוה) | #3 -->
                <div class="flex justify-center items-end gap-3 w-full">
                    {#each [2, 1, 3] as rank}
                        <div class="flex flex-col items-center gap-1.5 w-[30%] transition-transform {rank === 1 ? '-translate-y-4' : ''}">
                            {#if sec.showMedals}
                            <span class="font-black {rank === 1 ? 'text-2xl' : 'text-xl'}">
                                {rank === 1 ? '🥇' : rank === 2 ? '🥈' : '🥉'}
                            </span>
                            {/if}
                            <div class="rounded-full bg-white/10 border-2 border-dashed flex items-center justify-center text-gray-500 text-2xl
                                        {rank === 1 ? 'w-16 h-16 border-yellow-400/60' : 'w-14 h-14 border-white/20'}">
                                👤
                            </div>
                            <p class="text-gray-400 text-[11px] font-bold text-center leading-tight">{sec.label} #{rank}</p>
                            <div class="flex gap-0.5 text-amber-400 text-xs">★★★★★</div>
                            <p class="text-gray-500 text-[9px]">טרם דורג</p>
                        </div>
                    {/each}
                </div>
                <!-- שורה תחתונה: #4 | #5 ממורכז -->
                <div class="flex justify-center gap-3 w-full">
                    {#each [4, 5] as rank}
                        <div class="flex flex-col items-center gap-1.5 w-[30%]">
                            <span class="text-[11px] font-black text-gray-500">#{rank}</span>
                            <div class="w-14 h-14 rounded-full bg-white/10 border-2 border-dashed border-white/20 flex items-center justify-center text-gray-500 text-2xl">
                                👤
                            </div>
                            <p class="text-gray-400 text-[11px] font-bold text-center leading-tight">{sec.label} #{rank}</p>
                            <div class="flex gap-0.5 text-amber-400 text-xs">★★★★★</div>
                            <p class="text-gray-500 text-[9px]">טרם דורג</p>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- דסקטופ: גריד רגיל -->
            <div class="hidden md:grid md:grid-cols-5 md:gap-6">
                {#each [1,2,3,4,5] as rank}
                    <div class="flex flex-col items-center gap-3">
                        <div class="w-20 h-20 rounded-full bg-white/10 border-2 border-dashed border-white/20 flex items-center justify-center text-gray-500 text-3xl">
                            👤
                        </div>
                        <p class="text-gray-400 text-sm font-bold text-center">{sec.label} #{rank}</p>
                        <div class="flex gap-0.5 text-amber-400 text-lg">★★★★★</div>
                        <p class="text-gray-500 text-xs">טרם דורג</p>
                    </div>
                {/each}
            </div>
        </div>

        <div class="text-center mt-3 md:mt-4">
            <a href={sec.href} class="text-blue-400 hover:text-blue-300 text-sm font-bold transition-colors">לדף המלא ←</a>
        </div>
    </section>
    {/each}

</div>
