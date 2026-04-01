<template>
  <main id="plans" class="page page-plans width">
    <div id="facade" class="plans-facade">
      <img :src="baseUrl + 'imgs/photomontage-small.webp'" alt="Residence des Muses facade view" class="plans-facade-image" />
    </div>

    <div id="facade-table" class="plans-table">
      <div class="table plans-table-inner">
        <table class="avp-table avp-prix">
          <thead>
            <tr>
              <th class="column-1">Villa</th>
              <th class="column-2">Lot</th>
              <th class="column-3">{{ t('plans.rooms') }}</th>
              <th class="column-6">{{ t('plans.area') }}</th>
              <th class="column-7">Terrasse</th>
              <th class="column-8">{{ t('plans.garden') }}</th>
              <th class="column-18">{{ t('plans.priceWithoutParking') }}</th>
              <th class="column-21">{{ t('plans.status') }}</th>
              <th class="column-22">{{ t('plans.download') }}</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="v in villas" :key="v.lot" :class="['lot-' + v.lot, v.status === 'reserved' ? 'r' : 'd']">
              <td class="column-1">{{ v.name }}</td>
              <td class="column-2">{{ v.lot }}</td>
              <td class="column-3">{{ v.pieces }}</td>
              <td class="column-6">{{ v.surface }} m<sup>2</sup></td>
              <td class="column-7">{{ v.terrasse }} m<sup>2</sup></td>
              <td class="column-8">{{ v.jardin }} m<sup>2</sup></td>
              <td class="column-18">{{ t('plans.priceOnRequest') }}</td>
              <td class="column-21"><i></i><span>{{ t(`plans.statusValues.${v.status}`) }}</span></td>
              <td class="column-22">
                <a :href="baseUrl + v.planFile" download class="btn btn-plan-download">{{ t('plans.downloadPlan') }}</a>
              </td>
            </tr>
          </tbody>
        </table>
        <div class="plans-table-note">
          <p class="plans-table-note-text">{{ t('plans.note') }}</p>
        </div>
      </div>
    </div>

    <div class="table-btns">
      <div>
        <a :href="baseUrl + 'files/Residence_Des_Muses_Plans.pdf'" target="_blank" rel="noopener" class="btn">{{ t('plans.allPlans') }}</a>
      </div>
      <div>
        <a :href="baseUrl + 'files/Residence_Des_Muses-brochure.pdf'" target="_blank" rel="noopener" class="btn">{{ t('plans.brochure') }}</a>
      </div>
      <div>
        <router-link to="/contact" class="btn">{{ t('nav.contact') }}</router-link>
      </div>
    </div>
  </main>
</template>

<script setup>
import { inject } from 'vue'
import { useI18n } from '../composables/useI18n'
const baseUrl = inject('baseUrl', '/')
const { t } = useI18n()
const defaultPlanFile = 'files/Residence_Des_Muses_Plans.pdf'
const villas = [
  { name: 'ARTEMIS', lot: 'A', pieces: 4.5, surface: 127, terrasse: 25, jardin: '270,14', status: 'available', planFile: defaultPlanFile },
  { name: 'BRISEIS', lot: 'B', pieces: 4.5, surface: 127, terrasse: 25, jardin: '229,02', status: 'available', planFile: defaultPlanFile },
  { name: 'CASSIOPEE', lot: 'C', pieces: 4.5, surface: 128, terrasse: 25, jardin: '317,53', status: 'reserved', planFile: defaultPlanFile },
  { name: 'DEMETER', lot: 'D', pieces: 4.5, surface: 127, terrasse: 25, jardin: '308,70', status: 'available', planFile: defaultPlanFile },
  { name: 'ERATO', lot: 'E', pieces: 4.5, surface: 127, terrasse: 25, jardin: '248,91', status: 'available', planFile: defaultPlanFile },
  { name: 'FLORA', lot: 'F', pieces: 4.5, surface: 127, terrasse: 25, jardin: '252,10', status: 'available', planFile: defaultPlanFile },
  { name: 'GAIA', lot: 'G', pieces: 4.5, surface: 127, terrasse: 25, jardin: '318,75', status: 'available', planFile: defaultPlanFile },
  { name: 'HESTIA', lot: 'H', pieces: 4.5, surface: 128, terrasse: 25, jardin: '302,97', status: 'available', planFile: defaultPlanFile },
  { name: 'JUNON', lot: 'J', pieces: 4.5, surface: 127, terrasse: 25, jardin: '237,20', status: 'reserved', planFile: defaultPlanFile },
  { name: 'KALYPSO', lot: 'K', pieces: 4.5, surface: 127, terrasse: 25, jardin: '318,99', status: 'available', planFile: defaultPlanFile },
]
</script>

