<script lang="ts" setup>
import {ref, inject, watchEffect} from 'vue';
import {storeToRefs} from 'pinia';

import {utiliserÉtatInfos} from '/@/état/infos';
import ItemInfo from './ItemInfo.vue';

const étatInfos = utiliserÉtatInfos();
const {infos} = storeToRefs(étatInfos);
</script>

<template>
  <v-card
    class="text-start ma-2"
    variant="outlined"
    max-width="250"
  >
    <v-card-item>
      <v-card-title>
        {{ t('accueil.infos.titre') }}
      </v-card-title>
    </v-card-item>
    <v-card-text>
      <v-list
        style="overflow-y: auto"
        max-height="300"
      >
        <item-info
          v-for="info in infos"
          :key="info.id"
          :info="info"
          @fermer="() => étatInfos.effacerInfo(info.id)"
        />
      </v-list>
    </v-card-text>
  </v-card>
</template>
