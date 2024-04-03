<script>
import NewsItem from "../widgets/NewsItem.vue";
import NewsItemFooter from "../widgets/NewsItemFooter.vue";
import TimeStamp from "../widgets/TimeStamp.vue";
export default {
    data() {
        return {
            featuredArticle: {
                imageUrl: "https://images.performgroup.com/di/library/omnisport/79/d8/6c9b4b26f64a40ea89b7f69ccd088d40.jpg?t=-955230179&w=640",
                title: "Inter boss Simone Inzaghi reveals admiration for Diego Simeone ahead of clash",
                gmtTime: "2024-02-19T20:04:27.000Z",
                source: "FotMob",
                lead: "Simone Inzaghi and Diego Simeone, now boss of Atletico Madrid, helped Lazio win Serie A as players in 2000.",
                sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                pageURL: "https://www.fotmob.com/news/138lzxhk8mmsi1nflku3xemdte-inter-boss-simone-inzaghi-reveals-admiration-diego-simeone-ahead-clash"
            },
            articles: [
                {
                    imageUrl: "https://media.cnn.com/api/v1/images/stellar/prod/230221152426-palestinian-national-team-gfx.jpg?c=16x9&q=h_653,w_1160,c_fill/f_webp",
                    title: "All eyes were on Morocco at the last World Cup. Now, Palestinian national team wants a slice of the action at 2026 tournament",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "CNN",
                    lead: "The Palestinian team has never taken part in a World Cup tournament, but the territorys presence was very much in evidence at Qatar 2022.",
                    sourceIconUrl: "https://www.cnn.com/",
                    pageURL: "https://www.cnn.com/2023/02/22/football/palestianian-national-soccer-team-world-cup-spt-intl/index.html"
                },
                {
                    imageUrl: "https://digitalhub.fifa.com/transform/82e8b680-0d03-4b65-a91f-60696ebf97ea/GettyImages-1948403075?io=transform:fill,height:910,width:1536&quality=75",
                    title: "Goncalves: Angola has a lot to show the world",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "Fifa",
                    lead: "Coach Pedro Goncalves discusses exceptional AFCON campaign, shaping a team Angola's people can be proud of, and World Cup 26 ambitions.",
                    sourceIconUrl: "https://digitalhub.fifa.com/transform/157d23bf-7e13-4d7b-949e-5d27d340987e/WC26_Logo?io=transform:fill,height:105&quality=75",
                    pageURL: "https://www.fifa.com/fifaplus/en/tournaments/mens/worldcup/canadamexicousa2026/articles/pedro-goncalves-interview-angola"
                },
                {
                    imageUrl: "https://digitalhub.fifa.com/transform/d37fbd3a-9085-449b-9bc8-ab60e71f406d/MANCHESTER-ENGLAND-MAY-21-Ruben-Dias-of-Manchester-City-with-the-trophy-after-the-Premier-League-match-between-Manchester-City-and-Chelsea-FC-at-Etihad-Stadium-on-May-21-2023-in-Manchester-England-Photo-by-Michael-Regan-Getty-Images?io=transform:fill,width:1366&quality=75",
                    title: "Dias talks Portugal, Pep and World Cup dreams",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "Fifa",
                    lead: "Read what Ruben Dias told FIFA about Pep Guardiola, Erling Haaland and Roberto Martinez's in-form Portugal team.",
                    sourceIconUrl: "https://digitalhub.fifa.com/transform/157d23bf-7e13-4d7b-949e-5d27d340987e/WC26_Logo?io=transform:fill,height:105&quality=75",
                    pageURL: "https://www.fifa.com/fifaplus/en/tournaments/mens/worldcup/canadamexicousa2026/articles/ruben-dias-interview-portugal-manchester-city"
                },
                {
                    imageUrl: "https://a57.foxsports.com/statics.foxsports.com/www.foxsports.com/content/uploads/2024/02/1294/728/Pogba.jpg?ve=1&tl=1",
                    title: "Juventus midfielder Paul Pogba banned four years for doping",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "Fox Sports",
                    lead: "Juventus midfielder Paul Pogba was banned for the maximum penalty of four years by Italy's anti-doping court on Thursday after the World Cup winner tested positive for testosterone.",
                    sourceIconUrl: "https://www.foxsports.com/",
                    pageURL: "https://www.foxsports.com/stories/soccer/juventus-midfielder-paul-pogba-banned-for-four-years-for-doping"
                },
            ],
        }
    },
    components: {
        NewsItem,
        TimeStamp, 
        NewsItemFooter
    }
}
</script>

<template>
    <header class="WorldNewsHeader">
        <h1>World News</h1>
    </header>
    <div class="layout">
        <div class="featuredArticle">
            <div class="featuredImage">
                <img :src="featuredArticle.imageUrl" alt="featured article image" />
            </div>
            <div class="featuredArticleText">
                <h3>{{ featuredArticle.title }}</h3>
                <NewsItemFooter :article="featuredArticle" />
            </div>
        </div>
        <div class="articleGrid">
            <NewsItem v-for="article in articles" :newsItem="article" :key="article.title" />
        </div>
    </div>
</template>

<style scoped>
.WorldNewsHeader {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    margin: 0px 30px;
}
.featuredArticle {
    cursor: pointer;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: 1fr;
    padding: 0px 30px;
    position: relative;
}
.featuredImage {
    width: 100%;
    height: 100%;
    max-width: 640px;
}
.featuredImage>img {
    /* needs to also specify child to resize */
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.featuredArticleText {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    -webkit-box-pack: center;
    justify-content: center;
    background: var(--GlobalColorScheme-Background-background2);
    height: 100%;
    width: 100%;
    flex-direction: column;
    gap: 24px;
    padding: 20px;
}
.articleGrid {
    margin-top: 48px;
    padding: 0px 30px;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 40px 24px;
    -webkit-box-align: start;
    align-items: start;
}
</style>