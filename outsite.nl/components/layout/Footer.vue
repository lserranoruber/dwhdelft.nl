<i18n lang="yaml">
en:
  boardTitle: Board
  contactTitle: Contact
  board:
    - name: Feline
      pronouns: she/her
      role: President
      email: voorzitter
    - name: Chai
      pronouns: they/them
      role: Vice President
      email: vicevoorzitter
    - name: Alin
      pronouns: he/they
      role: Secretary
      email: secretaris
    - name: Nick
      pronouns: he/him
      role: Treasurer
      email: penningmeester
    - name: Jaye
      pronouns: any/all
      role: External Affairs
      email: extern
    - name: Lucia
      pronouns: they/them
      role: Internal Affairs
      email: intern
  confidential_counsellors: Confidential Counsellors
  copyright: Outsite is a part of
  links:
    my_dwh: 'My DWH: Log in as a member'
    sign_up: Join DWH as a member
nl:
  boardTitle: Bestuur
  contactTitle: Contact
  board:
    - name: Feline
      pronouns: zij/haar
      role: Voorzitter
      email: voorzitter
    - name: Chai
      pronouns: die/hun
      role: Vicevoorzitter
      email: vicevoorzitter
    - name: Alin
      pronouns: hij/die
      role: Secretaris
      email: secretaris
    - name: Nick
      pronouns: hij/hem
      role: Penningmeester
      email: penningmeester
    - name: Jaye
      pronouns: alle pronouns
      role: Commissaris Extern
      email: extern
    - name: Lucia
      pronouns: die/hun
      role: Commissaris Intern
      email: intern
  confidential_counsellors: Vertrouwenspersonen
  copyright: Outsite is onderdeel van
  links:
    my_dwh: 'My DWH: Inloggen als lid'
    sign_up: Inschrijven als DWH lid
</i18n>

<script setup>
import InstagramIcon from '#shared/assets/images/social/instagram.svg'
import YouTubeIcon from '#shared/assets/images/social/youtube.svg'
import GitHubIcon from '#shared/assets/images/social/github.svg'

const { t } = useT()

const socials = [
  { url: 'https://instagram.com/outsite_delft', icon: InstagramIcon },
  { url: 'https://www.youtube.com/@dwhdelft', icon: YouTubeIcon },
  { url: 'https://github.com/dwh-outsite/dwhdelft.nl', icon: GitHubIcon },
]

const links = [
  { name: 'Privacy', url: 'https://dwhdelft.nl/privacy' },
  { name: t('links.my_dwh'), url: 'https://my.dwhdelft.nl' },
]
</script>

<template>
  <div>
    <ElementsContainer class="text-white">
      <div class="md:flex">
        <div class="border-gray-600 py-8 md:w-2/3 md:border-r">
          <h3 class="mb-4 text-xl font-bold uppercase tracking-wider" v-text="t('boardTitle')" />

          <div class="md:flex">
            <div class="grid flex-1 auto-rows-min gap-6 xl:grid-cols-2">
              <LayoutFooterBoardMember
                v-for="member in t('board')"
                :key="member.name"
                :pronouns="member.pronouns"
                :role="member.role"
                :name="member.name"
                :email="`${member.email}@outsite.nl`"
              />
            </div>
            <div>
              <img
                src="~/assets/images/photos/boards/board23.png"
                class="mt-8 w-full shadow-xl md:mx-8 md:-mt-8 md:h-56 md:w-auto lg:h-64 xl:h-80"
              />
            </div>
          </div>
        </div>

        <div class="py-8 md:ml-4 xl:ml-10">
          <h3 class="mb-4 text-xl font-bold uppercase tracking-wider" v-text="t('contactTitle')" />

          <ContactOptions email="bestuur@outsite.nl" />

          <div class="mb-2 space-y-4">
            <LayoutFooterExternalLink href="https://my.dwhdelft.nl/signup">
              {{ t('links.sign_up') }}
            </LayoutFooterExternalLink>
            <LayoutFooterExternalLink href="https://dwhdelft.nl/lets-talk">
              {{ t('confidential_counsellors') }}
            </LayoutFooterExternalLink>
          </div>
        </div>
      </div>
    </ElementsContainer>

    <LayoutFooterCopyright :socials="socials" :links="links">
      <template #copyright>
        {{ t('copyright') }}
      </template>
    </LayoutFooterCopyright>
  </div>
</template>
