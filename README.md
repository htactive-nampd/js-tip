một số mẹo với js: 

    + sử dụng map cùng split("") để loop qua các kí tự trong một chuỗi
    
        for (i=0; i<string.length-1; ++i) {
            let char = str[i]
            // code
        }   

        có thể viết lại bằng:
        
        string.split("").map(char => {
            // code
        })

    + sử dụng template literals để nối chuỗi nhanh và trực quan hơn

        let subString = "ipsum quia dolor sit amet"

        let string = "Neque porro quisquam est qui dolorem "+ subString +" , consectetur, adipisci velit.."

        có thể được viết thành:

        let string = `Neque porro quisquam est qui dolorem ${subString} , consectetur, adipisci velit..`

    + gán giá trị mặc định cho parameter 
        
        function foo(a,b,c) {
            if (a === undefined) a = 1;
            if (b === undefined) b = 2;
            if (c === undefined) c = 3;

            //code
        }    

        có thể được viết lại thành: 

        function foo (a=1, b=2, c=3) {
            // code 
        }

    + gán giá trị cho biến số khi không xác định (undefined, null, "")

        if (a === undefined || a === null || a === "") {
            a = "defaul value"
        } 

        có thể được viết lại thành:   

        a = a || "default value" 

        hoặc 

        if (!a) a = "default value"

    + tham chiếu thuộc tính chưa được xác định trước của đối tượng:
        
        a = "ten thuoc tinh"

        object[a] 

    + Destructuring aliases - sử dụng để tạo một biến tham chiếu thuộc tính object một cách nhanh hơn:
        
        let foo = object.foo;

        có thể được viết thành:

        let {foo} = object;

    + Kiếm tra nhanh giá trị có trong mảng hay không:
        
        let arr = [1, 2, 3]
        
        arr.includes(2) // return true or false

    + tạo và thực thi function nhanh chóng:
        
        function foo (param) {
            // something
        }
        
        foo(param)

        có thể được viết thành:

        (function foo(param){
            // something
        })(param)

    + hoán đổi giá trị của hai biến:
        
        let a = "thing"
        let b = "otherThing"

        [a,b]=[b,a]

    + tự động truyền parameter

        function parseString(number) {
            return str.toString() // nhận vào số và trả về chuỗi
        }

        let array = [1,2,3,4]
    
        let stringArray = array.map(parseString) // thay vì array.map(number => { return parseString(number)}) 

        chú ý: hàm được gọi (parseString) phải chỉ có một tham số đầu vào (có thể sử dụng Destructuring Aliases để tăng số lượng tham số).
