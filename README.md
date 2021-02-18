# Class
## Create Class

<p>ازاي انشئ كلاس</p>

``` php
class nameOfClass{
//كده انا عملت كلاس 
}
```
<p>ازاي اخد من الكلاس اوبجكت</p>

``` php
$objName = new className();
//هنا انا عملت اوبجكت من الكلاس واقدر اعمل اكتر من اوبجكت عادي جدا
$objName2 = new className();
$objName3 = new className();
```
<p>اي كلاس بيبقا فيه حاجه اسمها خصائص ووظائف</p>

* خصائص == properties
* وظائف == methods

``` php

class Person{
    public $name; //Propertie
    public $age; //Propertie

    public function methodName(){
        // This Method
    }
}

```

<p>هنا انا عملت كلاس جديد و حطيت بداخله اتنين بروبيرتي و ميثود</p>
<p>طيب تعالا نعملكلاس جديد ونستخدم فيه الميثودث و البروبيرتيز</p>


``` php

class User{
    public $name; //Propertie
    public $age; //Propertie

    public function runing(){
        // This Method
        echo 'Yes You Can Runing';
    }
}
// تعالا بقا نجرب نطبع الكلام ده
// اول حاجه هعملها ان انا هعمل اوبجكت جديد من الكلاس ده

$user1 = new User();
// هنا انا عملت اوبجكت جديد اسمه يوزر واحد تعالا بقا نستخدمه

$user1->runing(); // will print Yes You Can Runing
// هنا انا استدعيت الميثود اللي اسمها يجري 

$user1->name = 'Abdulrahman';
$user1->age = 21;
// هنا انا حددت البروبيرتيز واديتها قيمه عايز اطبعها بقا

echo $user1->name; // will return Abdulrahmn
echo $user1->age; // will return 21
// هنا هيطبع البروبيرتز اللي انا حددتها دي

```
<p>طيب احنا قولنا ان احنا نقدر نعمل اكتر من اوبجكت تعالا نجرب احنا فوق عملنا اوبجكت اسمه يوزر واحد</p>

``` php
$user2 = new User();
 //هنا عملت اوبجكت تاني واقدر استخدمه عادي جدا زي اللي فوق واستخدم اي ميثود او اي بروبيرتي موجوده في الككلاس ده واقدر انشأ اوبجكتس زي ما انا عايز
$user3 = new User();
$user4 = new User();
//etc...
```
----
## Inheritance
<p>
الوراثه:

يعني ايه الواراثه يعني انا بعمل كلاس معين فيه خصائئص ووظائف معينه واقدر ان انا استخدم الكلاس ده في اي كلاس تاني يعني اللي هو اورث منه اي خصائص او وظائف موجوده ف الكلاس ده تعالو نشوف ازاي
</p>

``` php

class Car{
    public $name;
    public $color;
    public $power;

    public function speed(){
        echo 'Car Speed';
    }
}

class Toyota{
    public $id_number;

    public function fetures(){
        echo 'Car Fetures';
    }
}

```
<p>
دلوقت انا عملت كلاس اسمه كار وفيه كل خصائص اللي بتبقا موجوده في اي عربيه
وبعدين عملت كلاس تاني لعربيه نوعها تيوتا وضيفت عليها مميزاتها وخصائصها 
عايز بقا اخلي كلاس بتاع تيوتا ده يورث من كلاس العربيه عشان ما اكررش الخصائص  تاني في كل عربيه اعملها ف هعمل ايه بقا حاجه بسيطه جدا
</p>

``` php

class Car{
    public $name;
    public $color;
    public $power;

    public function speed(){
        echo 'Car Speed';
    }
}

class Toyota extends Car{
    public $id_number;

    public function fetures(){
        echo 'Car Fetures';
    }
}

```
<p>
كل اللي هعمله ان انا هكتب

extends 

واكتب اسم الكلاس اللي انا عايزه يورث منه زي المثال ده

لو جيت اعمل اوبجكت من كلاس اللي اسمه تويتا هلاقيه واخد كل الخصائص بتاعه الكلاس الاصلي بتاع العربيه
</p>

-----
## Access Modifiers
<p>
اليه الوصول او

حمايه الخصائص و الوظائف
</p>

* public // أقدر اوصلها من اي مكان
* private // مقدرش اوصلها
* protected //  مينفعش تأكسسه بشكل مباشر بس اقدر اوصلها بس في الكلاس بتعها او في الكلاس اللي وارث منها 

<p>مثال</p>

``` php

class User{
    public $name = 'Abdulrahman'; //ده اقدر اكسس من اي مكان
    protected $age = 21; //ده مقدرش اكسسه غير من الكلاس نفسه او الكلاس اللي وارث منه وميفعش اككسه بشكل مباشر
    private $password = '12345678'; //ده مينفعش اكسسه اصلا
}
/*
هنا في المثال ده انا عملت كلاس يوزر و حددت فيه خصائص 
اول خاصيه الاسم منطقي ان الاسم عادي اقدر اأكسسه عادي
لكن مش منطقي ان انا اأكسس الباسورد او شوفه ف اي مكان
و السن انا عملته بروتيكت عشان مقدر أكسسه غير ف الكلاس بتاعه او اللي وارث منه عشان لو هستخدمه ف اي حاجه
*/

$user1 = new User();
echo $user1->name; // هنا هيطبع الاسم عادي جدا
echo $user1->age; // هنا هيطلع ايرور عشان انا مينفعش اأكسس البروتيكت بشكل مباشر
echo $user1->password; // هنا مينفعش أاكسسه اصلا عشان هو برايفت

```
<p>تعالا نجرب مثال تاني عشان نستخدم البروتيكت</p>

``` php
class User {
    public $name = 'Abdulrahman';
    protected $password = '12345678';
}

class User1 extends User{
    
    public function getPassword(){
        echo $this->password; // this دي بتعود علي الاوبجكت اللي انا فيه
    }
}
// لو عملت اوبجكت بقا من يوزر1 وجربت استدعي الميثود اللي انا عملتها دي هتشتغل عادي جدا
$user1 = new User1();
$user1->getPassword(); //دي هتطبع الباسورد عادي جدا

```

-----
## $this

<p>
$this
دي كيورد بتعود علي الاوبكت اللي انا لسه مكريته تعالا ناخد مثال يوضح اكتر
</p>

``` php
class Toyota{
    protected $color = 'red';

    public function getColor(){
        echo $this->color;
    }
}
class Bmw{
    protected $color = 'black';
     public function getColor(){
        echo $this->color;
    }
}
class Volvo{
    protected $color = 'blue';
     public function getColor(){
        echo $this->color;
    }
}

$toyota = new Toyota();
echo $toyota->getColor(); //Will Return => red

$bmw = new Bmw();
echo $bmw->getColor(); //Will Return => black

$volvo = new Volvo();
echo $volvo->getColor(); //Will Return => blue

/*
هنا عرفنا ان 
$this
بتعود علي الاوبجكت اللي هي فيه
*/
```
----
## Abstract
<p>
دي قواعد انا بحطها في الكلاس ان اي كلاس تاني يورث من الكلاس ده لازم يمشي علي القواعد دي
تعالا ثاخد مثال عشان نفهم اكتر
</p>

``` php

class Car{
    abstract public function carSpeed();
    abstract public function carColor();
}

```
<p>
هنا انا عملت كلاس كار وحددت ليه خصائص لازم اي كلاس يورث منه يكون موجود فيه الخصائص دي مثال
</p>

``` php

class Car{
    abstract public function carSpeed();
    abstract public function carColor();
}

class Toyota extends Car{

    public function carSpeed(){
        echo '1000Km';
    }
    public function carColor(){
        echo 'Red'
    }

}

class Bmw extends Car{

    public function carSpeed(){
        echo '1500Km';
    }

}

$toyota = new Toyota();
echo $toyota->carSpeed(); // 1000km

$bmw = new Bmw(); // Will Return Erorr Cuse dosen't have carColor()

```

<p>
هنا انا عملت وراثه لتيوتا من الكلاس بتاع العربيه ف لو انا مضيفتش الخصائص اللي موجوده ف كلاس العربيه ده
هيطلعلي ايرور 
ف نعرف من كده ان انا اما احدد اي قواعد في  اي كلاس واجي اورث منه لازم اضيف كل القواعد اللي انا محددها
</p>

-----

## Encapsulation

<p>
عمليه التغلقيف يعني ايه
يعني مثلا انا لو عندي بروبيرتي اسمها باسورد وطبعا بم انها باسورد ف هتبقا برايفت
طيب تعالا نشوف مثال
</p>

``` php
class User{
    public $name;
    private $password;

    public function getPassword($password){
        $this->password = sha1($password);
    }
}

$user = new User();
echo $user->getPassword('123');

/*
تعالا بقا نشرح المثال ده:
اولا انا عملت كلاس اسمه يوزر وبعدين ضيفت فيه اتنين بروبيرتي واحد للاسم وواحد للباسورد والباسورد برايفت
ف دلوقت اللي انا عايزه عايز اعرض الباسورد وطبعا مينفعش اعرض الباسورد كده ف بعرضه مشفر تمام 
ف عملت ميثود تشفرلي الباسورد قبلما اجيبه 
طيب دلوقت بقا انا عملت اوبجكت جدبد من اليوزر وحاولت اعرض الباسود 123 مشفر ف هيطلعلي ايرور عشان طبعا البروبيرتي باسورد هي برايف اصلا ومش هيتفع اكسس عليها 
طيب ايه اللي المفروض اعمل المفروض اعمل عمليه تغليف  تعالا ناخد مثال عشان نفهم
*/
```
``` php
class User{
    public $name;
    private $password;

    public function setPassword($password){
        $this->password = sha1($password);
    }
    public function getPassword(){
       return $this->password;
    }
}

$user = new User();
$user->setPassword('123');
echo $user->getPassword();

/*
ده نفس المثال اللي فوق بس يختلف ان انا عملت تغليف للباسورد داخل الكلاس قبل ما اخرجه منه
عملت ميثود تحولي الباسورد لباسورد مشفر
وبعدين عملت ميثود تانيه تجيبلي الباسورد ده
ولما اجي استخدمها لازم استخد الاول الميثود اللي بتحول الباسورد وبعدين ابقا ارجعه
*/
```
-----

## Polymorphism

<p>
تعدد الاوجه يعني ايه بقا تعدد الاوجه ده
معناه ان انا عمل نفس الفانكشن بنفس الاسم ولكن بتؤدي وظيفه مختلفه  تعالا نشوف بتتكتب ازاي
</p>

``` php
//هنا ببدأ اعرفه بكلمه انترفيس و بعدين اعرف كل الفانكشنز اللي انا هكررهم علي حس وظيفتها
interface Cut{
    public function cut();
}

// هبدأ بقا اعمل كذا كلاس ويستخدم الفانكشن دي ولكن بوظيفه مختلفه

class Actor implements Cut{
    public function cut(){
        echo 'Actor Will Cut Acting';
    }
}

class Barber implements Cut{
    public function cut(){
        echo 'Barber Will Cut Heare';
    }
}

// هنا داوقت انا عملت كلاس جديد و هستخدم بقا الداله اللي اسمها كات ف لازم استدعي الكلاس بتعها ف بيتدعيه ازاي ب امبلمنت واكتب اسم الكلاس 
// طيب لو انا استدعيته ومكتبتش الداله يبقا كده هيطلع ايرور

$actor = new Actor();
$actor->cut(); //Return Actor Will Cut Acting
$barber = new Barber();
$barber->cut(); //Return Barber Will Cut Heare

/*
يبقا كده انا عرفت ان ممكناعمل ميثود واحده بنفس الاسم وتعمل وظيفه مختلفه عن كل واحده
*/
```
------
## Magic Methods
* #### __construct
<p>
دي داله بتتعمل في الكلاس واول اما انا انشئ الاوبجكت من الكلاس ده هتتنفذ علي طول
تعالا ناخد مثال:
</p>

```php
class Welcome{
    public function __construct(){
        echo 'Welcome';
    }
}

$wel = new Welcome(); // Return Welcome
// هنامن غير ما اقوله اطبع بقا اي حاجه هيقوم طابع اهلا اول اما انا عملت منه اوبجكت
```


* #### __destruct

<p>
دي زي الكونستراكت بس بتتنفذ اخر حاجه في الكلاس
</p>

```php
class Welcome{
    public function __destruct(){
        echo 'End';
    }
}

$wel = new Welcome(); // Return End
// دي هتتنفذ اخر حاجه ف الكلاس
```


















