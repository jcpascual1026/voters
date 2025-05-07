<script lang="ts">

    import Tempo from '$lib/Images/Temp.png';
    import { goto } from '$app/navigation';
    import VotersHeader from "../routes/Voters.svelte";

    type Candidate = {
        id: string;
        name: string;
        image: string;
        category: 'President' | 'Director for Graphics' | 'Secretary';
    };

    const candidates: Candidate[] = [
        { id: 'PC1', name: 'Juan P. Dela Cruz', image: Tempo, category: 'President' },
        { id: 'PC2', name: 'Juan P. Dela Cruz', image: Tempo, category: 'President' },
        { id: 'PC3', name: 'Juan P. Dela Cruz', image: Tempo, category: 'President' },
        { id: 'PC4', name: 'Juan P. Dela Cruz', image: Tempo, category: 'President' },

        { id: 'DGC1', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Director for Graphics' },
        { id: 'DGC2', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Director for Graphics' },
        { id: 'DGC3', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Director for Graphics' },
        { id: 'DGC4', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Director for Graphics' },

        { id: 'SC1', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Secretary' },
        { id: 'SC2', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Secretary' },
        { id: 'SC3', name: 'Juan P. Dela Cruz', image: Tempo, category: 'Secretary' }
    ];

    const filterCandidates = (category: 'President' | 'Director for Graphics' | 'Secretary'): Candidate[] => {
        return candidates.filter(candidate => candidate.category === category);
    };

  const Submit = () => {
    goto('/Submit');
  };

</script>

<VotersHeader />
<div class="m-5 pt-20">
    
    <div class="shadow-lg container py-2">
        <h1 class="text-center font-bold p-2 text-base sm:text-md md:text-xl lg:text-3xl">COLLEGE OF COMPUTER STUDIES ELECTION</h1>
    </div>

    <form action="" class="min-h-screen flex flex-col justify-between">
        <div class="shadow-lg container mb-8">
            <h1 class="text-center font-bold p-2 text-base sm:text-sm md:text-md lg:text-xl">ALGO President Candidates</h1>
            <div class="grid grid-cols-1 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
                {#each filterCandidates('President') as candidate}
                    <div class="pt-[3rem] pb-[2rem] px-3 bg-[#E3E9F9] rounded-xl shadow-xl p-4 w-full text-center my-2">
                        <img src={candidate.image} alt={candidate.name} class="mx-auto w-[9rem] h-[8.5rem] sm:w-[8rem] sm:h-[7rem] md:w-[7.5rem] md:h-[7rem]">
                        <h3 class="font-semibold my-4">{candidate.name}</h3>
                        <button type="button" class="border-[#02CC66] border flex px-5 gap-1 py-1 text-[#02CC66] font-semibold rounded-lg text-sm bg-white mx-auto">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" id={candidate.id} name="President_Candidates" value={candidate.id} class="w-5 h-5 border-2 border-gray-300 rounded-full checked:bg-[#02CC66] checked:border-[#02CC66] focus:ring-2 focus:ring-[#02CC66] cursor-pointer">
                                <span class="ml-2 text-[#02CC66] font-semibold">Vote</span>
                            </label>
                        </button>
                    </div>
                {/each}
            </div>
        </div>
    
        <div class="shadow-lg container mb-8">
            <h1 class="text-center font-bold p-2 text-base sm:text-sm md:text-md lg:text-xl">Director for Graphics Candidates</h1>
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
                {#each filterCandidates('Director for Graphics') as candidate}
                    <div class="pt-[3rem] pb-[2rem] bg-[#E3E9F9] rounded-xl shadow-xl p-4 w-full text-center mx-2 my-2">
                        <img src={candidate.image} alt={candidate.name} class="mx-auto w-[9rem] h-[8.5rem] sm:w-[8rem] sm:h-[7rem] md:w-[7rem] md:h-[7rem]">
                        <h3 class="font-semibold my-4">{candidate.name}</h3>
                        <button type="button" class="border-[#02CC66] border flex px-5 gap-1 py-1 text-[#02CC66] font-semibold rounded-lg text-sm bg-white mx-auto">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" id={candidate.id} name="Director_for_Graphics_Candidates" value={candidate.id} class="w-5 h-5 border-2 border-gray-300 rounded-full checked:bg-[#02CC66] checked:border-[#02CC66] focus:ring-2 focus:ring-[#02CC66] cursor-pointer">
                                <span class="ml-2 text-[#02CC66] font-semibold">Vote</span>
                            </label>
                        </button>
                    </div>
                {/each}
            </div>
        </div>

        <div class="shadow-lg container mb-8">
            <h1 class="text-center font-bold p-2 text-base sm:text-sm md:text-md lg:text-xl">ALGO Secretary Candidates</h1>
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
                {#each filterCandidates('Secretary') as candidate}
                    <div class="pt-[3rem] pb-[2rem] bg-[#E3E9F9] rounded-xl shadow-xl p-4 w-full text-center mx-2 my-2">
                        <img src={candidate.image} alt={candidate.name} class="mx-auto w-[9rem] h-[8.5rem] sm:w-[8rem] sm:h-[7rem] md:w-[7.5rem] md:h-[7rem]">
                        <h3 class="font-semibold my-4">{candidate.name}</h3>
                        <button type="button" class="border-[#02CC66] border flex px-5 gap-1 py-1 text-[#02CC66] font-semibold rounded-lg text-sm bg-white mx-auto">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" id={candidate.id} name="ALGO_Secretary_Candidates" value={candidate.id} class="w-5 h-5 border-2 border-gray-300 rounded-full checked:bg-[#02CC66] checked:border-[#02CC66] focus:ring-2 focus:ring-[#02CC66] cursor-pointer">
                                <span class="ml-2 text-[#02CC66] font-semibold">Vote</span>
                            </label>
                        </button>
                    </div>
                {/each}
            </div>
        </div>
    
        <!-- Submit Buttons Section -->
        <div class="m-5 text-center mb-8">
            <button type="button" class="px-7 py-2 rounded-lg bg-white text-blue-500 shadow-2xl cursor-pointer mr-2 font-semibold bottone1">Back</button>
            <button type="button" class="px-7 py-2 rounded-lg bg-blue-500 text-white shadow-2xl cursor-pointer mr-2 font-semibold bottone1">
                <a href="/Submit">Submit</a>
            </button>
        </div>
    </form>
    
</div>