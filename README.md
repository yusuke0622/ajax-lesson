# ajax-lesson
  都市名を入力したときに、その都市の天気予報を外部APIから取得し、Ajaxを用いて表示させるプログラムを作成

# APIサービスにアクセス
  https://openweathermap.org/  
  ログインしてkey取得

# JSONView
  https://api.openweathermap.org/data/2.5/weather?q=tokyo&units=metric&appid=取得したAPIキー

# 入力された都市名でWebAPIに天気情報をリクエスト
  $.ajax()は、Ajaxを実装するメソッド  
  url:では、APIにリクエストするURLを指定  
  dataTypeでは、レスポンスとして取得したいデータの型を指定(JSONで受け取るため　dataType : 'jsonp',）
  
#　通信成功した場合の処理
  $('#id名').text(JSONから欲しい値→JSONVIEW参照)の形で指定    
  ex)最高気温（temp_max）を取得したい場合は、$('#id名').text("data.JSONのオブジェクト名(main).プロパティ名(temp_max)");で取得  

#　天気のアイコンの表示
  $(要素名).attr(属性名,値);と指定すると、img要素にsrc属性とalt属性が追加される  
  アイコンを取得するURLは、http://openweathermap.org/img/w/"アイコン名".png  
  $('img').attr("src","http://openweathermap.org/img/w/" + data.weather[0].icon + ".png");  
  $('img').attr("alt",data.weather[0].main);
