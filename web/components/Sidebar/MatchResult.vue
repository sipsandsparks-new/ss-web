<script lang="ts" setup>
    interface Props {
        info: any,
        event: any,
        showType: any
    }
    const props = defineProps<Props>()

    const emit = defineEmits(['say-hi'])
</script>

<template>
    <div class="matchup-result-final-container d-flex flex-column gap-30 w-100">
        
        <template v-if="showType == 1 && info.matchup_owner">
            <div class="">
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <div v-if="info.matchup_owner.profile_picture" class="d-flex flex-column gap-20 mb-3">
                        <span class="fw-bold">Profile image </span>
                        <img :src="info.matchup_owner.profile_picture" width="100%" class="object-fit-contain" alt="">
                    </div>
                    <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Email Address: </span> {{ `${info.matchup_owner.email}` }}
                    </div>
                    <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Name: </span> {{ `${info.matchup_owner.first_name}` }}
                    </div>
                    
                    <div>
                        <b-button variant="primary" @click="emit('say-hi')">Say Hi!👋</b-button>
                    </div>
                </div>
            </div>
    
            <div v-if="info.matchup_owner.general_bio && info.matchup_owner.general_bio != ''">
                <div class="mb-2"><span class="fw-bold">GENERAL BIO:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_owner.general_bio && info.matchup_owner.general_bio != ''" class="white-space-break">
                        {{ info.matchup_owner.general_bio }}
                    </p>
                    <p v-else>No General bio provided!</p>
                </div>
            </div>
    
            <div v-if="info.matchup_owner.interests && info.matchup_owner.interests != ''" class="">
                <div class="mb-2"><span class="fw-bold">INTERESTS:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_owner.interests && info.matchup_owner.interests != ''" class="white-space-break">
                        {{ info.matchup_owner.interests }}
                    </p>
                    <p v-else>No Interests provided!</p>
                </div>
    
            </div>
    
            <div v-if="info.matchup_owner.facts && info.matchup_owner.facts != ''" clas="">
                <div class="mb-2"><span class="fw-bold">FUN FACTS:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_owner.facts && info.matchup_owner.facts != ''" class="white-space-break">
                        {{ info.matchup_owner.facts }}
                    </p>
                    <p v-else>No Fun facts provided!</p>
                </div>
    
            </div>

            
            
        </template>

        <template v-if="showType == 2 && info.matchup_user">
            <div class="">
                <div class="mb-2"><span class="fw-bold">USER INFORMATION:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <div v-if="info.matchup_user.profile_picture" class="d-flex flex-column gap-20 mb-3">
                        <span class="fw-bold">Profile image </span>
                        <img :src="info.matchup_user.profile_picture" width="100%" class="object-fit-contain" alt="">
                    </div>
                    <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Name: </span> {{ `${info.matchup_user.first_name}` }}
                    </div>
                    <!-- <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Gender: </span> {{ `${info.matchup_user.gender}` }}
                    </div>
                    <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Age: </span> {{ `${info.matchup_user.age ? info.matchup_user.age : 'Not provided'}` }}
                    </div>
                    
                    <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">height: </span> {{ `${info.matchup_user.height ? info.matchup_user.height : 'Not provided'}` }}
                    </div> -->
                    <!-- <div class="d-flex gap-10 mb-3">
                        <span class="fw-bold">Contact number: </span> {{ `${info.matchup_user.cell_phone ? info.matchup_user.cell_phone : 'Not provided'}` }}
                    </div> -->
                </div>
            </div>
    
            <div v-if="info.matchup_user.general_bio && info.matchup_user.general_bio != ''">
                <div class="mb-2"><span class="fw-bold">GENERAL BIO:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_user.general_bio && info.matchup_user.general_bio != ''" class="white-space-break">
                        {{ info.matchup_user.general_bio }}
                    </p>
                    <p v-else>No General bio provided!</p>
                </div>
            </div>
    
            <div v-if="info.matchup_user.interests && info.matchup_user.interests != ''" class="">
                <div class="mb-2"><span class="fw-bold">INTERESTS:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_user.interests && info.matchup_user.interests != ''" class="white-space-break">
                        {{ info.matchup_user.interests }}
                    </p>
                    <p v-else>No Interests provided!</p>
                </div>
    
            </div>
    
            <div v-if="info.matchup_user.facts && info.matchup_user.facts != ''" clas="">
                <div class="mb-2"><span class="fw-bold">FUN FACTS:</span></div>
                <div class="w-100 shadow-sm border border-radius-10 p-4">
                    <p v-if="info.matchup_user.facts && info.matchup_user.facts != ''" class="white-space-break">
                        {{ info.matchup_user.facts }}
                    </p>
                    <p v-else>No Fun facts provided!</p>
                </div>
    
            </div>
            
        </template>
    </div>
</template>

<style lang="scss" scoped>
    .matchup-result-final-container {
        .white-space-break {
            white-space: break-spaces;
        }
    }
</style>
