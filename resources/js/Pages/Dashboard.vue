<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import AdminLayout from '@/Layouts/AdminLayout.vue';
import DoctorLayout from '@/Layouts/DoctorLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout v-if="$page.props.auth.user.type === 'Patient'">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Welcome, {{$page.props.auth.user.name}}!</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">+ Create new appointment</div>
                </div>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">My appointments</div>
                </div>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">Calendar</div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>

    <DoctorLayout v-if="$page.props.auth.user.type === 'Doctor'">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Welcome, {{$page.props.auth.user.name}}!</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">My appointments</div>
                </div>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">Calendar</div>
                </div>
            </div>
        </div>
    </DoctorLayout>

    <AdminLayout v-if="$page.props.auth.user.type === 'Admin'">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Welcome, {{$page.props.auth.user.name}}!</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">Users module</div>
                </div>
            </div>
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 text-gray-900">Configuration</div>
                </div>
            </div>
        </div>
    </AdminLayout>
</template>
