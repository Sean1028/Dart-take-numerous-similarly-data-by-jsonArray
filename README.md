# Dart-take-numerous-similarly-data-by-jsonArray
import "dart:convert";

void main(){

  String stringOfjsonarray = """[1,2,3,4,5]""";
  List <dynamic> jsonarray= jsonDecode(stringOfjsonarray);
  
  for(int element in jsonarray){
    print (element);    
  }
  
  //加入資料
  jsonarray.add(6);
  String jsonArrayToString = jsonEncode(jsonarray);
  print (jsonArrayToString);
  
  //一個json array裡面裝載大量json object
  
  String LargejsonArrayOfObject = """[{"name":"小菜","age":"18"},{"name":"小美","age":"21"},
  {"name":"雲育鏈","age":"3"}]""";
  
  List <dynamic> LargejsonArray = jsonDecode(LargejsonArrayOfObject);
  print (LargejsonArray[0]["name"]); //取出第0個 object的name
 
  //將list的 資料型態存成map
  for(Map<String, dynamic> jsonObject in LargejsonArray ){
    print(jsonObject);
  }
  LargejsonArray.add({"name":"Flutter課程", "age":"1"});
  print(LargejsonArray);
  
}
