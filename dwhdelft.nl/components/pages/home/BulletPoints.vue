<i18n lang="yaml">
en:
  bullet_points:
    - title: Activism
      description: We are fighting for LGBTI+ acceptance in the region of Delft, we do this by speaking to local governments and organisations about their policy, and we participate with national actions for better trans care for LGBTI+ refugees.
      image: activism
    - title: Community
      description: From eating with other members to barnights and parties, DWH is the place to be for the queer community to meet each other. Come visit a few times and quickly you know some people.
      image: community
    - title: Events
      description: Throughout the year we organise a lot a big events. Karoake's, drag shows and LAN parties for ourselves, but also Purple Friday or Coming Out Day, to promote the LGBTI+ acceptance under the greater public.
      image: events
    - title: Support
      description: Next to all the fun activities, we are here to support each other. In our introductory group, young people can safely talk about their coming out stories, in the chats people can exchange advice about dating or their transition.
      image: support
nl:
  bullet_points:
    - title: Activisme
      description: Wij zijn voorvechters van LHBTI+ rechten in onze regio. We spreken de lokale overheden en organisaties over hun beleid, en doen mee met landelijke acties voor betere trans zorg of opvang van LHBTI+ vluchtelingen.
      image: activism
    - title: Community
      description: Van samen eten en board games tot baravonden en feesten, DWH is de place to be om als queer community elkaar te ontmoeten. Kom een paar keer langs en al snel is er altijd wel iemand die je kent.
      image: community
    - title: Evenementen
      description: Door het jaar heen organiseren we tal van activiteiten. Karaoke's, drag shows en LAN parties voor onszelf, maar ook Paarse Vrijdag of Coming-Outdag. Zo promoten we LHBTI+ acceptatie onder het grotere publiek.
      image: events
    - title: Support
      description: Naast alle leuke activiteiten, zijn we er voor elkaar. In onze kennismakingsgroep praten jongeren veilig over hun coming out, en in de chatgroepen kan men advies uitwisselen over daten of hun transitie.
      image: support
</i18n>

<script setup>
const { t } = useT()

const { image } = useDynamicImages(import.meta.glob('~/assets/images/photos/bullets/*', { eager: true }))
const requireImage = (name) => image(`bullet_${name}`)
</script>

<template>
  <ElementsContainer>
    <div class="grid gap-6 xl:grid-cols-2">
      <PhotoCard
        v-for="point in t('bullet_points')"
        :key="point.title"
        :title="point.title"
        :description="point.description"
        :image="requireImage(point.image)"
      />
    </div>
  </ElementsContainer>
</template>
