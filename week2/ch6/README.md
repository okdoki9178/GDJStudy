# 객체
## 6.1 객체 개요
> 자바스크립트 자료형 -> number, string, boolean, function, undefined 그리고 object!
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
    </code>
  </pre>