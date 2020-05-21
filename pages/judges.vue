<template lang="pug">
  .judges
    HeaderMenu()
    SubPageTopTitle(:title="'Judges & Mentors'")
    .container
      .judges_message {{message}}
    SectionTitle(:title="'Judges'")
    .container
      .judges_wrapper(v-for="(jud,jud_key) in judges" :key="`jud_${jud_key}`")
        a(:href="jud.link").judge
          img.judge_picture(v-if="jud.img" :src="require(`~/assets/images/${jud.img}.png`)")
          .judge_content
            .judge_content--name {{jud.name}}
            .judge_content--affiliate
              .office(v-for="(affi,affi_key) in jud.affiliate" :key="`about_${affi_key}`")
                p {{affi}}
            .judge_content--about(v-for="(about,about_key) in jud.about" :key="`about_${about_key}`")
              p {{about}}
    SectionTitle(:title="'Mentors'")
    .container
      .judges_wrapper(v-for="(men,men_key) in mentors" :key="`men_${men_key}`")
        a(:href="men.link").judge
          img.judge_picture(v-if="men.img" :src="require(`~/assets/images/${men.img}.png`)")
          .judge_content
            .judge_content--name {{men.name}}
            .judge_content--affiliate
              .office(v-for="(affi,affi_key) in men.affiliate" :key="`about_${affi_key}`")
                p {{affi}}
            .judge_content--about(v-for="(about,about_key) in men.about" :key="`about_${about_key}`")
              p {{about}}
    Footer

</template>

<script>
// components
import HeaderMenu from '~/components/molecules/HeaderMenu'
import SubPageTopTitle from '~/components/atoms/SubPageTopTitle'
import SectionTitle from '~/components/atoms/SectionTitle.vue'
import Footer from '~/components/organisms/Footer.vue'

export default {
  components: {
    HeaderMenu,
    SubPageTopTitle,
    SectionTitle,
    Footer
  },

  head() {
    return {
      title: 'Judges',
      titleTemplate: '%s - ONLINE INTERN CONTEST 2020 #3'
    }
  },

  data() {
    return {
      publish: true,
      message: 'オンコン（略称）の審査員およびメンターの方々をご紹介します！',
      judges: [
        {
          name: '中川 卓也',
          affiliate: ['株式会社 アカデミックギャングスター', '代表取締役'],
          img: 'nakagawa_takuya',
          about: [
            '1983年京都大学卒業。',
            '事業会社を経て、外資系投資銀行に勤務。',
            '・キダー・ピーボディ証券（GEキャピタル）外国株式部',
            '・バークレイズ証券 キャピタルマーケット部 ダイレクター',
            '・HSBC証券 資本市場部門 マネージング・ダイレクター',
            '・みずほ証券 グローバル投資銀行部門 事業開発総括部長',
            '・ネスレ日本株式会社 総務人事本部 人材・組織開発部長',
            '・プルータス・コンサルティング エグゼクティブ・ダイレクター',
            '等を歴任。',
            'グローバルマーケッツ、Ｍ＆Ａ、デット/エクイティファイナンス、デリバティブ金融複合商品、ストラクチャードファイナンス・セキュリタイゼーション、ＰＥ・ヘッジファンドの資金調達、ＩＲ・コーポレートガバナンスアドバイス、組織・人材開発プログラム企画実施、などに従事。',
            '事業会社、機関投資家の事業戦略、資本・財務政策、資金調達、議決権行使基準、人事人材政策へのアドバイスにより顧客の企業価値向上に携わる。中央官庁、自治体、アカデミア、取引所、などと連携しながら各種制度改正や地方経済活性化にも携わる。'
          ],
          link: 'https://twitter.com/AcademicGang'
        },
        {
          name: '渋谷 修太',
          affiliate: ['フラー株式会社', '代表取締役社長兼CEO'],
          img: 'shibuya_shuta',
          about: [
            '1988年生。新潟県出身。',
            '国立長岡工業高等専門学校卒業後、筑波大学へ編入学。',
            'グリー株式会社にてソーシャルゲーム最盛期にマーケティング事業に従事した後、2011年11月フラー株式会社を創業、代表取締役社長兼CEOに就任。',
            '2016年には世界有数の経済誌Forbesにより30歳未満の重要人物「30アンダー30」、世界を担う若手リーダーを集うG1新世代リーダー・サミットメンバーに選出。',
            '新潟経済同友会所属。'
          ],
          link: 'https://twitter.com/shibushuta'
        },
        {
          name: '駒村 和彦',
          affiliate: [
            '野村総合研究所',
            'ソーシャルイノベーショングループ　マネージャー（上級コンサルタント）'
          ],
          img: 'komamura_kazuhiko',
          about: [
            '2007年　東京大学大学院修了（工学）',
            '日本政府のイノベーション政策・スタートアップ支援政策の立案・実行をコンサルタントとして支援。',
            '日本のイノベーション促進を支援すべく、「ものづくりスタートアップのための契約ガイドライン」や、「大企業と研究開発型ベンチャーのオープンイノベーション促進のためのガイドライン」等の成果物の作成などを手がけている。',
            'また、2018年より「新潟イノベーションプログラム」のプロジェクトリーダーとして新潟における0→1の事業構想支援に尽力。',
            'NRIレポート「都市におけるイノベーション創発機能～イノベーション拠点都市における価値創造活動の進め方 ～」（2020年4月）',
            '米国Georgetown UniversityにてMBA取得（2017年）',
            '在学中にNonmarket Strategy（非市場戦略）の認定を取得。',
            'コンサルティング業務の傍ら、上智大学や二松学舎大学等で非常勤講師（経営学など）として教鞭もとる。',
            '趣味はサッカー。高校時代は神奈川県選抜、社会人リーグで活動後、現在は少年サッカーのコーチ。'
          ],
          link:
            'https://www.nri.com/-/media/Corporate/jp/Files/PDF/knowledge/publication/region/2019/07/2_vol192.pdf?la=ja-JP&hash=723A9E269C2D5E3E7635CFBC29FBF4CAE946BFE2'
        }
      ],
      mentors: [
        {
          name: '菅野 流飛',
          affiliate: ['株式会社 高専キャリア教育研究所 代表取締役'],
          img: 'kanno_ryuhi',
          about: [
            '東京高専卒業。東京工業大学大学院博士課程3年次中退。',
            'Speee入社後、リブセンス事業部長、リクルート事業開発など、 IT業界でベンチャー企業から大手企業まで渡り歩いてきた。',
            '2015年よりライフワークとして東京高専でのキャリア教育セミナーや高専特化型クラウドファンディングなどを運営。2017年に高専キャリア教育研究所を設立。',
            '2019年にみらい創造機構と資本業務提携を締結し、エンジニア向けキャリア開発プラットフォームの構築を推進している。',
            '情報経営イノベーション専門職大学客員教授。高専DCON実行委員会。東京高専同窓会役員。'
          ],
          link: 'https://twitter.com/RyuhiKanno'
        },
        {
          name: '兼城 駿一郎',
          affiliate: ['株式会社 高専キャリア教育研究所 CTO'],
          img: 'kaneshiro_shunichiro',
          about: [
            '沖縄高専専攻科卒業。在学中に全国高専プログラミングコンテストと起業家甲子園で準優勝し、学生起業も経験。',
            'リクルートホールディングスに新卒入社後、開発組織の立ち上げ・新規事業開発・スタートアップの買収を経験。',
            'リクルート在籍中にSNS分析のスタートアップmisosilを創業し、代表取締役に就任。VCや金融機関からの資金調達や黒字化を実現し役員を退任。',
            '現在は高専キャリア教育研究所のCTOを務めつつ、Jidoca Technologiesの代表取締役としてスタートアップの技術顧問や事業開発・アプリケーション開発の支援を行っている。'
          ],
          link: 'https://twitter.com/pinkroot'
        },
        {
          name: '青山 陽',
          affiliate: ['Amazon Data Services Japan K.K'],
          img: 'Aoyama_Yo',
          about: [
            '電気主任技術者連盟 副会長',
            '2009年 奈良高専電気工学科卒業',
            '2016年 関西電力株式会社入社 送電線保守及び設計に7年間従事',
            '2016年 SBエナジー株式会社入社 再生可能エネルギー発電所建設プロジェクトマネージャー、新規事業コンテスト優秀賞獲得し事業化を経験、SoftBank vision fundにてサウジアラビア及びインドの電源構成検討',
            '2019年 日本たばこ産業株式会社入社 関西工場での電気主任技術者業務に従事、電気主任技術者連盟設立',
            '2020年 Amazon Data Service Japan入社 大規模データセンターの電力エンジニアとして勤務'
          ],
          link: 'https://twitter.com/kosen_go'
        }
        // },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.judges_message {
  margin: 24px 0 48px;
  width: 100%;
  text-align: center;
  font-size: 2rem;
}

.judges_wrapper {
  text-align: center;
  padding: 48px 0 60px;
}

.judge {
  @include flex($justifyContent: flex-start, $alignItems: flex-start);
  background: $white;
  transition: 0.3s $ease-out-1;
  transform: translateY(0);
  padding: 32px;
  text-decoration: none;
  &::before {
    content: '';
    display: block;
    background: $white;
  }
  &:hover {
    transform: translateY(-8px);
    box-shadow: 0 4px 16px rgba($black, 0.1);
  }
  &_picture {
    flex-shrink: 0;
    width: 320px;
    height: 320px;
  }
  &_content {
    margin: 0 0 0 40px;
    text-align: left;
    color: $black;
    &--name {
      font-family: $noto-sans;
      font-size: 2.4rem;
      margin-bottom: 20px;
    }
    &--affiliate {
      font-family: $noto-sans;
      font-size: 2rem;
      margin-bottom: 24px;
    }
    &--about {
      font-family: $noto-sans;
    }
  }
}

@media screen and (max-width: $md) {
  .judges_message {
    font-size: 1.8rem;
    text-align: left;
  }
}

@media screen and (max-width: $tb) {
  .judge {
    &_picture {
      width: 240px;
      height: 240px;
    }
    &_content {
      &--name {
        font-size: 2rem;
      }
      &--affiliate {
        font-size: 1.8rem;
      }
      &--about {
        font-size: 1.4rem;
      }
    }
  }
}

@media screen and (max-width: 780px) {
  .judge {
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    &_picture {
      width: 360px;
      height: 360px;
      margin-bottom: 24px;
    }
    &_content {
      text-align: center;
      margin: 0 40px;

      &--about {
        text-align: left;
      }
    }
  }
}
@media screen and (max-width: $sm) {
  .judge {
    &_picture {
      width: 240px;
      height: 240px;
      margin-bottom: 24px;
    }
    &_content {
      &--affiliate {
        font-size: 1.6rem;
      }
    }
  }
}

@media screen and (max-width: 540px) {
  .judge {
    padding: 24px;
    &_content {
      margin: 0;
    }
  }
}
</style>
