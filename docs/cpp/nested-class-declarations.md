---
title: "Объявления вложенных классов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], объявление"
  - "объявления, класс"
  - "объявления, вложенные классы"
  - "объявление классов"
  - "вложенные классы"
  - "вложенные классы, объявление"
ms.assetid: c02e471d-b7f9-41b8-8ef6-2323f006dbd5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Объявления вложенных классов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс можно объявить в области другого класса.  Такой класс называется вложенным классом. Считается, что вложенные классы находятся в области включающего класса и доступны для использования внутри этой области.  Для обращения ко вложенному классу из области, отличной от непосредственно включающей его области, следует использовать полное имя.  
  
 В следующем примере показано, как объявить вложенные классы.  
  
```  
// nested_class_declarations.cpp  
class BufferedIO  
{  
public:  
   enum IOError { None, Access, General };  
  
   // Declare nested class BufferedInput.  
   class BufferedInput  
   {  
   public:  
      int read();  
      int good()  
      {  
         return _inputerror == None;  
      }  
   private:  
       IOError _inputerror;  
   };  
  
   // Declare nested class BufferedOutput.  
   class BufferedOutput  
   {  
      // Member list  
   };  
};  
  
int main()  
{  
}  
```  
  
 `BufferedIO::BufferedInput` и `BufferedIO::BufferedOutput` объявлены внутри `BufferedIO`.  Эти имена классов не видимы за пределами области класса `BufferedIO`.  Однако объект типа `BufferedIO` не содержит объекты типа `BufferedInput` или `BufferedOutput`.  
  
 Вложенные классы могут непосредственно использовать имена, имена типов, имена статических членов и перечислители только из включающего класса.  Для использования имен других членов класса необходимо использовать указатели, ссылки или имена объектов.  
  
 В предыдущем примере `BufferedIO` к перечислению `IOError` можно получить доступ непосредственно с помощью функций\-членов во вложенных классах `BufferedIO::BufferedInput` или `BufferedIO::BufferedOutput`, как показано в функции `good`.  
  
> [!NOTE]
>  Вложенные классы объявляют только типы в пределах области класса.  Они не создают объекты по вложенном классе.  В предыдущем примере объявляется два вложенных класса, но не объявляются объекты этих типов классов.  
  
 Исключением из видимости области объявления вложенного класса является объявление имени типа вместе с опережающим объявлением.  В этом случае имя класса, объявленное с помощью опережающего объявления, видимо за пределами включающего класса, при этом область определена как наименьшая включающая область вне класса.  Пример:  
  
```  
// nested_class_declarations_2.cpp  
class C  
{  
public:  
    typedef class U u_t; // class U visible outside class C scope  
    typedef class V {} v_t; // class V not visible outside class C  
};  
  
int main()  
{  
    // okay, forward declaration used above so file scope is used  
    U* pu;  
  
    // error, type name only exists in class C scope  
    u_t* pu2; // C2065  
  
    // error, class defined above so class C scope  
    V* pv; // C2065  
  
    // okay, fully qualified name  
    C::V* pv2;  
}  
```  
  
## Права доступа во вложенных классах  
 Вложение класса в другой класс не предоставляет особые права доступа к функциям\-членам вложенного класса.  Аналогичным образом, функции\-члены включающего класса не имеют особых прав доступа к членам вложенного класса.  
  
## Функции\-члены во вложенных классах  
 Функции\-члены, объявленные во вложенных классах, могут быть определены в области файла.  Предыдущий пример можно было бы записать следующим образом:  
  
```  
// member_functions_in_nested_classes.cpp  
class BufferedIO  
{  
public:  
    enum IOError { None, Access, General };  
    class BufferedInput  
    {  
    public:  
        int read(); // Declare but do not define member  
        int good(); //  functions read and good.  
    private:  
        IOError _inputerror;  
    };  
  
    class BufferedOutput  
    {  
        // Member list.  
    };  
};  
// Define member functions read and good in  
//  file scope.  
int BufferedIO::BufferedInput::read()  
{  
   return(1);  
}  
  
int BufferedIO::BufferedInput::good()  
{  
    return _inputerror == None;  
}  
int main()  
{  
}  
```  
  
 В предыдущем примере синтаксис *полное\-имя\-типа* используется для объявления имени функции.  Объявление:  
  
```  
BufferedIO::BufferedInput::read()  
```  
  
 означает "функция `read`, которая является членом класса `BufferedInput`, который находится в области класса `BufferedIO`". Поскольку в этом объявлении используется синтаксис *полное\-имя\-типа*, возможны конструкции следующего вида:  
  
```  
typedef BufferedIO::BufferedInput BIO_INPUT;  
  
int BIO_INPUT::read()  
```  
  
 Данное объявление эквивалентно предыдущему, но в нем используется имя `typedef` вместо имен классов.  
  
## Дружественные функции во вложенных классах  
 Считается, что дружественные функции, объявленные во вложенном классе, находятся в области вложенного, а не включающего класса.  Поэтому дружественные функции не получают особых прав доступа к членам или функциям\-членам включающего класса.  Если требуется использовать имя, объявленное во вложенном классе, в дружественной функции, и дружественная функция определена в области видимости файла, используйте полные имена типов, как показано ниже.  
  
```  
// friend_functions_and_nested_classes.cpp  
  
#include <string.h>  
  
enum  
{  
    sizeOfMessage = 255  
};  
  
char *rgszMessage[sizeOfMessage];  
  
class BufferedIO  
{  
public:  
    class BufferedInput  
    {  
    public:  
        friend int GetExtendedErrorStatus();  
        static char *message;  
        static int  messageSize;  
        int iMsgNo;  
   };  
};  
  
char *BufferedIO::BufferedInput::message;  
int BufferedIO::BufferedInput::messageSize;  
  
int GetExtendedErrorStatus()  
{  
    int iMsgNo = 1; // assign arbitrary value as message number  
  
    strcpy_s( BufferedIO::BufferedInput::message,  
              BufferedIO::BufferedInput::messageSize,  
              rgszMessage[iMsgNo] );  
  
    return iMsgNo;  
}  
  
int main()  
{  
}  
```  
  
 В следующем коде показана функция `GetExtendedErrorStatus`, объявленная в качестве дружественной функции.  В функции, определенной в области видимости файла, сообщение копируется из статического массива в член класса.  Обратите внимание, что для оптимальной реализации функции `GetExtendedErrorStatus` рекомендуется объявить ее следующим образом.  
  
```  
int GetExtendedErrorStatus( char *message )  
```  
  
 В предыдущем интерфейсе несколько классов могут использовать службы этой функции, передав адрес памяти, в которую требуется скопировать сообщение об ошибке.  
  
## См. также  
 [Классы и структуры](../Topic/Classes%20and%20Structs%20\(C++\).md)