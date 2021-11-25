<template>
  <div>
    <div class="container">
      <div class="container2">
        <h2>＜ホーム＞　Tweet一覧</h2>
          <!--
            <div class="container3">
              <form @submit.prevent="tweet">
                <div class="form-group">
                  <div class="tweet">
                    <input type="text" name="content" class="form-control" placeholder="" style="width:200px; height:200px;">
                  </div>
                  <button type="submit" class="btn btn-primary">シェアする</button>
                </div>
              </form>
          </div>
    <h1 style="margin-top:50px;">Todoリスト</h1>
    -->

    <table class="table table-striped" style="max-width:1000px; margin-top:20px;">

      <thead>
        <tr>
          <th>Tweeter</th>
          <th>シェアした日</th>
          <th>Tweet</th>
          <th>編集</th>
          <!--<th>更新日</th>-->
          <th>削除</th>
        </tr>
      </thead>

      <tbody>
        <!--@foreach ($tweets ?? '' as $tweet)-->
        <tr>
          <!--<p>{{ $tweet.tweet.id }}</p>-->
          <!--<p>{{ $tweet.tweet.created_at }}</p>-->
          <!--<p>{{ $tweet.tweet.content }}</p>-->
          <td>
            <form action="" method="post">
          <!--    {{ csrf_field() }}
              {{ method_field('PUT') }}
          -->
              <input type="text" name="content" class="task" value="">
          <td><button type="submit" class="btn btn-primary">編集</button></td>
          </form>
          </td>

          <td>
            <form action="" method="post">
            <!--  {{ csrf_field() }}
              {{ method_field('delete') }}
              -->
              <button type="submit" class="btn btn-danger">削除</button>
            </form>
          </td>
        </tr>
        <!--@endforeach-->
        <!--ページネーションのページ別リンク追記-->
        <!--{{ $todos ?? ''->links() }}-->
      </tbody>
    </table>
  </div>
    <div>
      <Nuxt />
    </div>
    </div>
  </div>

</template>

<script>
export default {
  layout: "sidebar2"
}
</script>

<style>
.container {
  padding: 30px;
  position: absolute;
  left: 30%;
  top: 0;
}
p {
  color: white;
  text-align: right;
}
h2 {
  color: white;
}
table {
  color: white;
}
</style>
