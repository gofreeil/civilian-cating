<div class="space-y-10 py-8">
    <div class="text-center">
        <h1 class="text-3xl md:text-4xl font-black text-white mb-3">
            דירוג שופטים
        </h1>
    </div>

    <div class="bg-white/5 border border-white/10 rounded-2xl p-6">
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-6">
            {#each [1,2,3,4,5] as i}
                <div class="flex flex-col items-center gap-3">
                    <div class="w-20 h-20 rounded-full bg-white/10 border-2 border-dashed border-white/20 flex items-center justify-center text-gray-500 text-3xl">
                        👤
                    </div>
                    <p class="text-gray-400 text-sm font-bold">שופט #{i}</p>
                    <div class="flex gap-0.5 text-amber-400 text-lg">★★★★★</div>
                    <p class="text-gray-500 text-xs">טרם דורג</p>
                </div>
            {/each}
        </div>
    </div>

    <div class="text-center">
        <a href="/" class="text-blue-400 hover:text-blue-300 text-sm transition-colors">← חזרה לדף הבית</a>
    </div>
</div>
