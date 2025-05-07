<script>
    let user = "Jc Pascual";
    import Tempo from '$lib/Images/Temp.png';
    
    function logout() {
        console.log("Logging out...");
    }
</script>

<nav
    class="flex items-center justify-between px-6 sm:px-10 py-4 sm:py-[30px] bg-white fixed top-0 left-0 w-full z-50 shadow-md"
>
    <div class="flex items-center space-x-3 min-w-0">
        <img
            src={Tempo}
            alt="OCTA Logo"
            class="h-10 sm:h-[47px] w-auto object-contain shrink-0"
        />

        <span
            class="font-bold text-gray-800 whitespace-nowrap truncate tracking-[2px] sm:tracking-[3px] cursor-default text-sm sm:text-base md:text-xl lg:text-2xl"
        >
            OCTA
        </span>
    </div>

    <div class="flex items-center gap-4 sm:gap-8">
        <p class="text-sm sm:text-lg text-black font-bold truncate max-w-[90px] sm:max-w-none">
            {user}
        </p>

        <button on:click={logout} class="cursor-pointer focus:outline-none">
            <div class="sm:hidden bg-[#3778DA] rounded-lg p-2 text-white">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a2 2 0 11-4 0v-1m0-8V7a2 2 0 114 0v1" />
                </svg>
            </div>

            <div
                class="hidden sm:flex items-center bg-[#3778DA] rounded-lg px-6 py-2.5 text-md font-bold text-white shadow-sm"
            >
                Log out
            </div>
        </button>
    </div>
</nav>
