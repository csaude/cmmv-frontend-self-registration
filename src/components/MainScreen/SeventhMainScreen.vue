<template>
  <transition-group
    appear
    enter-active-class="animated slideInRight"
    leave-active-class="animated slideOutLeft absolute-top"
  >
    <q-slide-item @left="$emit('previousScreen')" left-color="white">
      <template v-slot:left>
        <q-icon name="reply" />
      </template>
      <q-item>
        <div key="seventhScreen" class="q-gutter-md row items-start">
          <img
            src="~src/assets/07Escolha.png"
            style="height: auto; max-width: 100%"
          />
          <div class="row q-pa-md">
            <q-btn
              flat
              round
              color="primary"
              icon="west"
              @click="$emit('previousScreen')"
            />
          </div>
          <div class="row q-mb-lg">
            <q-item-label class="text-h4">{{
              'Faça uma escolha consciente'
            }}</q-item-label>
          </div>
          <div class="row">
            <p>A circuncisão médica é gratuita, segura e rápida.</p>
            <p>
              Passe a palavra ao seu irmão/amigo/vizinho/parente, com 15 à 49
              anos de idade.
            </p>

            <p>
              Para mais informação sobre a circuncisão médica masculina
              voluntária

              <q-btn
                class="link"
                flat
                color="primary"
                text-color="primary"
                @click="$emit('showInformationScreen')"
              >
                clique aqui
              </q-btn>
            </p>
          </div>
        </div>
      </q-item>
    </q-slide-item>
    <div class="q-pa-md">
      <div class="row justify-center">
        <q-btn
          class="q-mr-md"
          unelevated
          rounded
          color="primary"
          label="Marcar Consulta"
          @click="$emit('createAppointment')"
        />
        <q-btn
          unelevated
          rounded
          color="green"
          label="Pesquisar Consulta"
          @click="$emit('searchAppointment')"
        />
      </div>
    </div>
    <transition
      appear
      enter-active-class="animated fadeIn"
      leave-active-class="animated fadeOut"
    >
      <seventhScreenInstruction />
    </transition>
  </transition-group>
</template>

<script setup>
import seventhScreenInstruction from 'components/UserInstructions/SeventhMainScreenInstruction.vue';
import pageContent from 'components/MainScreen/Content.vue';
</script>

<style>
.link {
  text-decoration: underline; /* Remove button default styling */
  cursor: pointer;
  margin: 0; /* Adjust margin as needed */
  padding: 0; /* Adjust padding as needed */
}
.link .q-btn__label {
  text-decoration: underline;
}
</style>
