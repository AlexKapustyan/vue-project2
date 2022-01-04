<template>
  <div id="post-page" class="post-page">
    <div class="post">
      <h1>{{ post.title }}</h1>
      <p>{{ post.body }}</p>
      <span>{{ formatedPostDate }}</span>
      <hr />
    </div>
    <div class="comments">
      <div
        :id="`comment-${commentsList.id}`"
        v-for="commentList in commentsList"
        :key="commentList.id"
        class="comments__item"
      >
        <h3>{{ commentList.name }}</h3>
        <span>{{ commentList.email }}</span>
        <p>{{ formatedCommentText(commentList.body) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PostPage",
  data: () => ({
    post: {
      id: 1,
      title: "Eum et est occaecati",
      body: "Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit.",
      postDate: new Date(),
    },
    commentsList: [
      {
        postId: 1,
        id: 1,
        name: "id labore ex et quam laborum",
        email: "Eliseo@gardner.biz",
        body: "laudantium enim quasi est quidem magnam voluptate ipsam eos\ntempora quo necessitatibus\ndolor quam autem quasi\nreiciendis et nam sapiente accusantium",
      },
      {
        postId: 1,
        id: 2,
        name: "quo vero reiciendis velit similique earum",
        email: "Jayne_Kuhic@sydney.com",
        body: "est natus enim nihil est dolore omnis voluptatem numquam\net omnis occaecati quod ullam at\nvoluptatem error expedita pariatur\nnihil sint nostrum voluptatem reiciendis et",
      },
      {
        postId: 1,
        id: 3,
        name: "odio adipisci rerum aut animi",
        email: "Nikita@garfield.biz",
        body: "quia molestiae reprehenderit quasi aspernatur\naut expedita occaecati aliquam eveniet laudantium\nomnis quibusdam delectus saepe quia accusamus maiores nam est\ncum et ducimus et vero voluptates excepturi deleniti ratione",
      },
      {
        postId: 1,
        id: 4,
        name: "alias odio sit",
        email: "Lew@alysha.tv",
        body: "non et atque\noccaecati deserunt quas accusantium unde odit nobis qui voluptatem\nquia voluptas consequuntur itaque dolor\net qui rerum deleniti ut occaecati",
      },
      {
        postId: 1,
        id: 5,
        name: "vero eaque aliquid doloribus et culpa",
        email: "Hayden@althea.biz",
        body: "harum non quasi et ratione\ntempore iure ex voluptates in ratione\nharum architecto fugit inventore cupiditate\nvoluptates magni quo et",
      },
    ],
  }),
  methods: {
    formatedCommentText(str) {
      let upletterString = str[0].toUpperCase() + str.slice(1);
      return str.length > 20
        ? upletterString.slice(0, 20) + "..."
        : upletterString;
    },
  },
  computed: {
    formatedPostDate() {
      const month = [
        "Января",
        "Февраля",
        "Марта",
        "Апреля",
        "Мая",
        "Июня",
        "Июля",
        "Августа",
        "Сентября",
        "Октября",
        "Ноября",
        "Декабря",
      ];
      let date = this.post.postDate;
      let day = date.getDate();
      let monthNumber = date.getMonth();
      let year = date.getFullYear();
      return `${day} ${month[monthNumber]}, ${year}`;
    },
  },
};
</script>

<style scoped lang="scss">
  .post-page {
		padding: 20px;
		
		.comments__item {
			background-color:  rgb(14, 137, 238);
			padding: 10px;
			border-radius: 5px;
			margin-bottom: 5px;
			color: #fff;
		}
	}
</style>