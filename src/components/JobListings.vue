<script setup>
import { ref, defineProps, onMounted, reactive } from 'vue';
import JobListing from './JobListing.vue';
import { RouterLink } from 'vue-router';
import axios from 'axios';
import PulseLoader from 'vue-spinner/src/PulseLoader.vue';

defineProps({
    limit: Number,
    showButton: {
        type: Boolean,
        default: false
    }
});

const state = reactive({
    jobs: [],
    isLoading: true,
});

onMounted(async () => {
    try {
        const response = await axios.get('/api/jobs');
        state.jobs = response.data;
    } catch (error) {
        console.error('Error fetching jobs:', error);
    } finally {
        state.isLoading = false;
    }
});
</script>

<template>
    <section class="bg-blue-50 px-4 py-10">
        <div class="container-xl lg:container m-auto">
            <h2 class="text-3xl font-bold text-green-500 mb-6-text-center">
                Browse Jobs
            </h2>
            <!-- Show loading spinner while loading is true -->
             <div v-if="state.isLoading" class="text-gray-500 text-center">
                <PulseLoader :loading="state.isLoading" color="#4F46E5" size="15px" />

             </div>

            <!-- Show jobs when done loading -->
            <div v-else class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div v-for="job in state.jobs.slice(0, limit || state.jobs.length)" :key="job.id" class="job-item">
                    <JobListing :job="job" />
                </div>
            </div>
        </div>
    </section>
    <section v-if="showButton" class="block bg-black text-white text-center py-4 px-6 rounded hover:bg-gray-800">
        <RouterLink to="/jobs">View All Jobs</RouterLink>
    </section>
</template>