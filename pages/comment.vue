<template>

  <div class="container">
      <div class="container">
        <div class="container2">
          <h2>＜コメント＞</h2>

    <table class="table table-striped" style="max-width:1000px; margin-top:20px;">

      <thead>
        <tr>
          <th>Tweeter</th>
          <th>シェアした日</th>
          <th>Tweet</th>
          <!--<th>編集</th>-->
          <!--<th>更新日</th>-->
          <!--<th>削除</th>-->
        </tr>
      </thead>

      <tbody>
        <!--@foreach ($tweets ?? '' as $tweet)-->
        <tr>
          <!--<td>{{$tweet->name}}</td>-->
          <!--<td>{{$tweet->content}}</td>-->
          <!--<td>{{$tweet->created_at}}</td>-->
          <!--<td>{{$todo->updated_at}}</td>-->
          <td>
          <!--
            <form action="" method="post">
              {{ csrf_field() }}
              {{ method_field('PUT') }}
              <input type="text" name="content" class="task" value="">
          <td><button type="submit" class="btn btn-primary">編集</button></td>
          </form>
          </td>
          <td>
            <form action="" method="post">
            <!-- {{ csrf_field() }}
              {{ method_field('delete') }}
              <button type="submit" class="btn btn-danger">削除</button>
            </form>
            -->
          </td>
        </tr>
        <!--@endforeach-->
        <!--ページネーションのページ別リンク追記-->
        <!--{{ $todos ?? ''->links() }}-->
      </tbody>
    </table>

      <form action="/todos" method="post">
      <!--  {{csrf_field()}}
        @if ($errors->has('content'))
        <tr>
          <th></th>
          <td>
            <p>{{$errors->first('content')}}</p>
          </td>
        </tr>
        @endif-->
        <div class="form-group2">

          <!--<label>やることを追加してください</label>-->
          <input type="text" name="content" class="form-control" placeholder="" style="width:675px;">
          <button type="submit" class="btn btn-primary">コメントする</button>
        </div>
      </form>
    </div>


    <!--<h1 style="margin-top:50px;">Todoリスト</h1>-->
  </div>
    <div>
      <Nuxt />
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
}
p {
  color: white;
  text-align: left;
}
h2 {
  color: white;
}
table {
  color: white;
}
.form-group2 button {
  margin-top: 10px;
  position: absolute;
  right: 0;
  bottom: -10px;
}
</style>