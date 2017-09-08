# 객체
## 6.1 객체 개요 + 6.2 속성과 메서드
> 자바스크립트 자료형 -> number, string, boolean, function, undefined 그리고 object!
> object는 변수, 메서드 둘다 멤버로 할당 가능하다.
> object의 멤버에 접근시 object명.멤버명 or object["멤버명"]
> 객체지향 언어의 class처럼 사용하기
  
>> JAVA
  <pre>
    <code>
      public class Product {
        public name;
        public type;
        public from;

        public void showInfo(){
          System.out.println(this.name + "//" + this.type + "//" + this.from)
        }
      }

      //main 호출시
      Product product = new Product();
      product.name = "7D 건조망고";
      prodcut.type = "당절임";
      product.form = "필리핀";
      product.showInfo();

      //결과
      7D 건조망고//당절임//필리핀
    </code>
  </pre>

>> EcmaScript
  <pre>
    <code>
      var product = {};
      product.name = "7D 건조망고";
      // product["name"] = "7D 건조망고";
      product.type = "당절임";
      product.from = "필리핀";
      product.showInfo = function(){
        //console.log(this.name + "//" + this.type + "//" + this.from)
        console.log(`${this.name} // ${this.type} // ${this.from} `)
      }

      product.showInfo();

      // or

      var product2 = {
        name : "7D 건조망고",
        type : "당절임",
        from : "필리핀",
        showInfo : function(){
          //console.log(this.name + "//" + this.type + "//" + this.from)
          console.log(`${this.name} // ${this.type} // ${this.from} `)
        }
      }

      product2.showInfo();
    
    // class Product 는 다음챕터에서..
    </code>
  </pre>

## 6.3 객체와 반복문 
> 단순 for문으론 모든 속성에 접근하기 힘든 점들을 향상된 포문(in을 이용)을 이용하여 쉽게 사용이 가능하다.
>> in 없이 출력하기
>><pre>
  <code>
    var product = {
      name : "7D 건조망고",
      type : "당절임",
      from : "필리핀"
    }

    var output = "";
    var keys = Object.keys(product);
    for(var i = 0; i < keys.length; i++ ){
      output += `${keys[i]} : ${product[keys[i]]} \n`;
    }
    console.log(output)
  </code>
</pre>
>> in 을 이용하여 출력하기
<pre>
  <code>
    var product = {
      name : "7D 건조망고",
      type : "당절임",
      from : "필리핀"
    }

    var output = "";
    for(var key in product){
      output += `${key} : ${product[key]} \n`;
    }
    console.log(output);
  </code>
</pre>


## 6.4 객체 관련 키워드 
> in 키워드 
>> object에 key가 포함되는지 확인하는 키워드
<pre>
  <code>
    var product = {
      name : "7D 건조망고",
      type : "당절임",
      from : "필리핀"
    }
      
    var output = "";
    output += `name 속성은 product객체에 ${'name' in product ? "있습니다" : "없습니다"} \n`;
    output += `type 속성은 product객체에 ${'type' in product ? "있습니다" : "없습니다"} \n`;
    output += `size 속성은 product객체에 ${'size' in product ? "있습니다" : "없습니다"} \n`;
    console.log(output)
  </code>
</pre>
> with 키워드
<pre>
  <code>

      //before
      var product = {
        name : "7D 건조망고",
        type : "당절임",
        from : "필리핀"
      }
      
      var output = "";
      output += `name 속성은 product객체에 ${'name' in product ? "있습니다" : "없습니다"} \n`;
      output += `type 속성은 product객체에 ${'type' in product ? "있습니다" : "없습니다"} \n`;
      output += `size 속성은 product객체에 ${'size' in product ? "있습니다" : "없습니다"} \n`;
      console.log(output)
  </code>
</pre>