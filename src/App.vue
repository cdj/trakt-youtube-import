<template>
  <q-layout view="lHh Lpr lFf">
    <!-- <q-header elevated class="glossy">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      class="bg-grey-2"
    >
      <q-list>
        <q-item-label header>Essential Links</q-item-label>
        <q-item clickable tag="a" target="_blank" href="https://quasar.dev">
          <q-item-section avatar>
            <q-icon name="school" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Docs</q-item-label>
            <q-item-label caption>quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://github.com/quasarframework/">
          <q-item-section avatar>
            <q-icon name="code" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Github</q-item-label>
            <q-item-label caption>github.com/quasarframework</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://chat.quasar.dev">
          <q-item-section avatar>
            <q-icon name="chat" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Discord Chat Channel</q-item-label>
            <q-item-label caption>chat.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://forum.quasar.dev">
          <q-item-section avatar>
            <q-icon name="forum" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Forum</q-item-label>
            <q-item-label caption>forum.quasar.dev</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable tag="a" target="_blank" href="https://twitter.com/quasarframework">
          <q-item-section avatar>
            <q-icon name="rss_feed" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Twitter</q-item-label>
            <q-item-label caption>@quasarframework</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer> -->

    <q-page-container>
      <ConnectTrakt />
      <LoadGoogleTakout />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";
import ConnectTrakt from "./components/ConnectTrakt.vue";
import LoadGoogleTakout from "./components/LoadGoogleTakout.vue";

export default {
  name: "LayoutDefault",

  components: {
    ConnectTrakt,
    LoadGoogleTakout,
  },

  setup() {
    return {
      leftDrawerOpen: ref(false),
    };
  },
  data() {
    return {
      author: {
        name: "John Doe",
        books: [
          "Vue 2 - Advanced Guide",
          "Vue 3 - Basic Guide",
          "Vue 4 - The Mystery",
        ],
      },
      youtubeVideos: {},
      // get shows here https://trakt.tv/shows/popular?countries=us&networks=YouTube
      mappingSettings: {
        matchDatetimeTolerance: 1000 * 60 * 60 * 24 * 7,
      },
      mapping: [
        {
          channel: "FirstWeFeast",
          channelId: "UCPD_bxCRGpmmeQcbe2kpPaA",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Hot Ones$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEMIIK3r4Se1dOZWSZzUSadfZ",
              traktShow: "https://trakt.tv/shows/hot-ones",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Pizza Wars$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEMIaiU6w7qY-H9O849R8niHr",
              traktShow: "https://trakt.tv/shows/pizza-wars",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Burger Scholar Sessions$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEMIkFTtpY-Vn0Kjj_LQ0pE0M",
              traktShow: "https://trakt.tv/shows/burger-scholar-sessions",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Snacked$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEMIrmTcAqwSBGBFCNioeKgPk",
              traktShow: "https://trakt.tv/shows/snacked",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Tacos Con Todo$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEMIguYDVq6DWeijfWuqAnsVO",
              traktShow: "https://trakt.tv/shows/tacos-con-todo",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Hungry For More$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLAzrgbu8gEML7FAsmfuwZMsjn18cUhvPV",
              traktShow: "https://trakt.tv/shows/hungry-for-more",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| The Burger Show$/i,
                  groups: ["epName"],
                },
              ],
              traktShow: "https://trakt.tv/shows/the-burger-show",
            },
          ],
        },
        {
          channel: "screenjunkies",
          channelId: "UCOpcACMWblDls9Z6GERVi1A",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^Honest Trailers \| (.+)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PL86F4D497FD3CACCE",
              traktShow: "https://trakt.tv/shows/honest-trailers",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Power Levels$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLFWHlH4koGZDzg8R4zuSWU-6ynZ_XxX9D",
              traktShow: "https://trakt.tv/shows/power-levels",
            },
            {
              limitToPlaylist: "PLFWHlH4koGZACo8-Npd2eSvJk7mH-wrtO",
              traktShow: "https://trakt.tv/shows/screen-junkies-movie-fights",
            },
          ],
        },
        {
          channel: "fandomgames",
          channelId: "UCf6J9yokPS0ys456jvjLBGQ",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^Honest Game Trailers \| (.+)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLHkNwtRZFo2g74tWgElcOO2T3WWbN7Aga",
              traktShow: "https://trakt.tv/shows/honest-game-trailers",
            },
          ],
        },
        {
          channel: "WOWPresents",
          channelId: "UCUUUpaMp8DV6KUOfQwoIiLg",
          series: [
            {
              titleMatch: [
                {
                  pattern:
                    /^UNHhhh[^"“”\w\d]+(?:ep|episode)?[^"“”\w\d]*(\d+)[^"“”\w\d]+["“”]([^"“”]+)["“”]/i,
                  groups: ["epAbsNum", "epName"],
                },
                {
                  pattern: /^UNHhhh\W+(?:ep|episode)?\W*(\d+)\W+(.+)$/i,
                  groups: ["epAbsNum", "epName"],
                },
                {
                  pattern: /^UNHhhh[^"“”]+["“”]([^"“”]+)["“”]/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLhgFEi9aNUb2BNrIEecCGXApgeX7Yjwz8",
              traktShow: "https://trakt.tv/shows/unhhhh",
            },
          ],
        },
        {
          channel: "rocketjump",
          channelId: "UCDsO-0Yo5zpJk575nKXgMVA",
          series: [
            {
              titleMatch: [
                {
                  pattern:
                    /^Video Game High School(?: \(VGHS\))\W+s(?:eason)?(\d+)\W*e(?:pisode|p)?\W+(\d+)/i,
                  groups: ["seaNum", "epNum"],
                },
              ],
              limitToPlaylist: "PLsMtUWKCmBPRFzqglpk4YQlNFy8wzSXBN",
              traktShow: "https://trakt.tv/shows/power-levels",
            },
          ],
        },
        {
          channel: "NBCNews",
          channelId: "UCeY0bbntWzzVIaj2z3QigXg",
          series: [
            {
              titleMatch: [
                {
                  pattern:
                    /^(?:NBC )?Nightly News(?:\W+Broadcast\W+Full|\W+Full\WBroadcast)\W+(\D+\.? \d+(?:th|st|rd|nd)?(?:, \d+)?)(?: \| NBC Nightly News)?$/i,
                  groups: ["airDate"],
                },
              ],
              orInPlaylist: "PL0tDb4jw6kPymVj5xNNha5PezudD5Qw9L",
              traktShow: "https://trakt.tv/shows/nbc-nightly-news",
            },
          ],
        },
        {
          channel: "BuzzFeedUnsolvedNetwork",
          channelId: "UCKijjvu6bN1c-ZHVwR7-5WA",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^(?:BuzzFeed Unsolved: )?(.+)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLD8iUdp33PqQuSYl9EljppQERLUlsDtR5",
              traktShow: "https://trakt.tv/shows/buzzfeed-unsolved-2016",
            },
          ],
        },
        {
          channel: "LizzieBennet",
          channelId: "VLPL6690D980D8A65D08",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^(.+) - Ep: (\d+)$/i,
                  groups: ["epName", "epAbsNum"],
                },
              ],
              limitToPlaylist: "PL6690D980D8A65D08",
              traktShow: "https://trakt.tv/shows/the-lizzie-bennet-diaries",
            },
          ],
        },
        {
          channel: "CartoonHangover",
          channelId: "UCIA9jUDnKVMYc4SmqTxcwqg",
          series: [
            {
              titleMatch: [
                {
                  pattern:
                    /^"(.+)" - Bee and PuppyCat - Ep\. (\d+) - (?:Full Episode - Cartoon Hangover|Cartoon Hangover - Full Episode)$/i,
                  groups: ["epName", "epNum"],
                },
              ],
              limitToPlaylist: "PL2DcNkn8HAwQLcXTiDB876bU13hT0OhsZ",
              traktShow: "https://trakt.tv/shows/bee-and-puppycat/seasons/1",
            },
            {
              titleMatch: [
                {
                  pattern: /^"(.+)" - Bravest Warriors (?:Season |S)(\d+) Ep. (\d+) (?:- Season Finale )?(?:- Full Episode )?- Cartoon Hangover$/i,
                  groups: ["epName", "epNum", "seaNum"],
                },
                {
                  pattern: /^(.+) \(Bravest Warriors - Ep\. (\d+) Season (\d+) On Cartoon Hangover\)$/i,
                  groups: ["epName", "epNum", "seaNum"],
                },
                {
                  pattern: /^(.+) - Bravest Warriors (Minisode \d+) On Cartoon Hangover$/i,
                  groups: ["epName", "epNamePrefix"],
                },
              ],
              limitToPlaylist: "PL2DcNkn8HAwRCsyrLzeLW8e0ScNNvadcE",
              traktShow: "https://trakt.tv/shows/bravest-warriors",
            },
          ],
        },
        {
          channel: "AngryNintendoNerd",
          channelId: "UC0M0rxSz3IF0CsSour1iWmw",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^(.+) - Angry Video Game Nerd \(AVGN\)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PL2B009153AC977F90",
              traktShow: "https://trakt.tv/shows/angry-video-game-nerd",
            },
          ],
        },
        {
          channel: "UCGt7X90Au6BV8rf49BiM6Dg",
          channelId: "UCGt7X90Au6BV8rf49BiM6Dg",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^(.+) \((\d{4})\)$/i,
                  groups: ["epName", "epYear"],
                },
                {
                  pattern: /^(.+)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PLeTICGf2vpVLGahXICXMoigdAyemAzf_f",
              traktShow: "https://trakt.tv/shows/3-2009",
            },
          ],
        },
        {
          channel: "BuzzFeedVideo",
          channelId: "UCpko_-a4wgz2u_DgDgd9fqA",
          series: [
            {
              titleMatch: [],
              limitToPlaylist: "PL5vtqDuUM1DmXwYYAQcyUwtcalp_SesZD",
              traktShow: "https://trakt.tv/shows/worth-it",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+)\W+Mom In Progress$/i,
                  groups: ["epName"],
                },
                {
                  pattern: /^(.+)$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PL5vtqDuUM1Dnqiaj8uHrtqx_XXw_x1w9Z",
              traktShow: "https://trakt.tv/shows/mom-in-progress",
            },
            {
              titleMatch: [],
              limitToPlaylist: "PL5vtqDuUM1DmEDlQxKJi9i-j0wLWB-2zK",
              traktShow: "https://trakt.tv/shows/the-try-guys",
            },
          ],
        },
        {
          channel: "roosterteethanimation",
          channelId: "UCpko_-a4wgz2u_DgDgd9fqA",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^Season (\d+), (?:Chapter|Episode) (\d+) - (.+) \| Red vs\. Blue$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
                {
                  pattern: /^Season (\d+), Chapter (\d+) \| Red vs\. Blue$/i,
                  groups: ["seaNum", "epNum"],
                },
              ],
              limitToPlaylist: "PLUBVPK8x-XMjLwdUZdZzGBk2XZBJvJK7V",
              traktShow: "https://trakt.tv/shows/red-vs-blue",
            },
            {
              titleMatch: [
                {
                  pattern: /^Season (15), Episode (\d+) - (.+) \| Red vs. Blue$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL2vBnPCQT4WJJN9TBT0nET3cqeJ62ukZ1",
              traktShow: "https://trakt.tv/shows/red-vs-blue/seasons/15",
            },
            {
              titleMatch: [
                {
                  pattern: /^Season (16), Episode (\d+) - (.+) \| Red vs. Blue$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL2vBnPCQT4WJSsoYpLbEUx7M3CD5pzPn-",
              traktShow: "https://trakt.tv/shows/red-vs-blue/seasons/16",
            },
            {
              titleMatch: [
                {
                  pattern: /^Red vs. Blue: Singularity \| Episode (\d+): (.+)$/i,
                  groups: ["epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL2vBnPCQT4WJlBeJ8GSqJHyP32MK66dxz",
              traktShow: "https://trakt.tv/shows/red-vs-blue/seasons/17",
            },
            {
              titleMatch: [
                {
                  pattern: /^Red vs.? Blue: Zero \| Episode (\d+): (.+)$/i,
                  groups: ["epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL2vBnPCQT4WLMMbyAWmhFTJGXtOprJJvS",
              traktShow: "https://trakt.tv/shows/red-vs-blue/seasons/18",
            },
            {
              titleMatch: [
                {
                  pattern: /^(.+) \| Family Shatters$/i,
                  groups: ["epName"],
                },
              ],
              limitToPlaylist: "PL2vBnPCQT4WJ9X0mXOvFq65mHoQ8CVorM",
              traktShow: "https://trakt.tv/shows/red-vs-blue/seasons/19",
            },
          ],
        },
        {
          channel: "TheGuild",
          channelId: "UCt9S9nd8hATsfRjRlrcyklw",
          series: [
            {
              titleMatch: [
                {
                  pattern: /^The Guild - Episode (\d+): (.+)$/i,
                  groups: ["epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J6mzp6UD2TNtWpYo3Bh5ULA",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
            {
              titleMatch: [
                {
                  pattern: /^The Guild - S(2) Ep ?(\d+): (.+)$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J4f86rQC6TtFp_MmfArga7S",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
            {
              titleMatch: [
                {
                  pattern: /^The Guild - S(3) Ep ?(\d+): (.+)$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J7L9oyvVZT14-xMT9RanZr_",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
            {
              titleMatch: [
                {
                  pattern: /^The Guild - S(4) Ep ?(\d+): (.+)$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J4NcMx2iIs2fr4_-elWrjRY",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
            {
              titleMatch: [
                {
                  pattern: /^The Guild - S(5) Ep ?(\d+): (.+)$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J5vmS5Bi_Qj67_ZKUchBsrG",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
            {
              titleMatch: [
                {
                  pattern: /^The Guild - S(6) Ep ?(\d+): (.+)$/i,
                  groups: ["seaNum", "epNum", "epName"],
                },
              ],
              limitToPlaylist: "PL5wBMT6Z03J5OeVPFYR3gxtFME_hppiLA",
              traktShow: "https://trakt.tv/shows/the-guild",
            },
          ],
        },
        {
          channel: "tryguys",
          channelId: "UCpi8TJfiA4lKGkaXs__YdBA",
          series: [
            {
              titleMatch: [],
              traktShow: "https://trakt.tv/shows/the-try-guys",
            },
          ],
        },
      ],
    };
  },
  computed: {
    // a computed getter
    publishedBooksMessage() {
      // `this` points to the component instance
      return this.author.books.length > 0 ? "Yes" : "No";
    },
  },
};
</script>
