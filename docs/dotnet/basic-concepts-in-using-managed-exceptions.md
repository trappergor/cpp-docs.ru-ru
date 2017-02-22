---
title: "Основные принципы использования управляемых исключений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally - ключевое слово, управляемые исключения"
  - "catch - блоки"
  - "исключения, управляемая"
  - "создание исключений, управляемые исключения"
  - "обработка исключений try-catch"
  - "обработка исключений try-catch, управляемые приложения"
  - "Visual C++, обработка управляемых исключений"
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Основные принципы использования управляемых исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе обсуждается обработка исключений в управляемых приложениях.  То есть приложение, компилировано с параметром компилятора **\/clr**.  
  
## В этом разделе  
  
-   [При порождении исключения в \/clr](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Блоков try\/catch для расширений CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## Примечания  
 Если компилировать с параметром **\/clr**, можно обрабатывать исключения среды CLR, так и стандартное [Обработка исключений C\+\+.](../cpp/cpp-exception-handling.md) и [структурной обработки исключений](../cpp/structured-exception-handling-c-cpp.md) \(ОНА\).  Исключение CLR любое исключение, вызванное управляемым типом.  Класс [System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) предоставляет много полезных методов для обработки исключения среды CLR и рекомендуется в качестве базового класса для определяемых пользователем классов исключений.  
  
 Типы, производные от перехвата исключений интерфейса не поддерживаются в **\/clr**.  Кроме того, среда CLR не допускает перехватывать исключения переполнения стека; исключение переполнения стека завершения процесса.  
  
 Различия в дополнительных сведений в обработке исключений в управляемом и неуправляемых приложениях см. в разделе [Различия в расширении функциональности обработки исключений в управляемых расширениях для C\+\+.](../dotnet/differences-in-exception-handling-behavior-under-clr.md)  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> При порождении исключения в \/clr  
 Выражение хода C\+\+ расширен генерирует дескриптор типа CLR.  В следующем примере создается пользовательский тип исключения, а затем создает экземпляр этого типа.  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 Тип значения должен быть упакован перед делегатом:  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Блоков try\/catch для расширений CLR  
 Те же **try**\/блоковую структуру **catch** можно использовать для перехвата и CLR и собственные исключения:  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### Output  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### Порядок уничтожения объектов C\+\+.  
 Происходит при возникновении любых объектов C\+\+ с деструкторами, которые могут находиться в стеке времени выполнения между функцию функцией и обработки функцией.  Так как типы CLR размещаются в куче, развертывание не применяется к ним.  
  
 Порядок событий для создание исключения следующим образом:  
  
1.  Выполнения просматривает стек и соответствующее предложение catch или, в случае SEH, за исключением фильтра для SEH, для перехвата исключения.  Предложения " catch " ведет поиск сначала словарном в порядке, а затем динамически вниз стека вызова.  
  
2.  Как только правильный обработчик найден, стек освобождается до указанного положения.  Для каждого вызова функции в стеке разрушаны ее локальные объекты и \_\_finally блоки, выполняются с вложенным.  
  
3.  После того как стек освобождается, предложение catch выполняется.  
  
### Перехват неуправляемые типы  
 Если тип неуправляемого объекта возникает, он будет создавать программу\-оболочку с исключением типа [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx).  Поиск соответствующего предложения **catch**, 2 возможности.  
  
-   Если собственный тип C\+\+ встречается, исключение развернуто и сравнивается с столкнутому типу.  Это сравнение позволяет собственный тип C\+\+, следует перехватывать обычным способом.  
  
-   Однако если предложение **catch** типа **SEHException** или любого базовых классов анализируется сначала, предложение перехватит исключение.  Поэтому необходимо установить все предложения catch перехвата собственные типы C\+\+ перед всеми предложениями catch типов среды CLR.  
  
 Обратите внимание, что  
  
```  
catch(Object^)  
```  
  
 и  
  
```  
catch(...)  
```  
  
 оба уловят любой тип, включая SEH исключения.  
  
 Если неуправляемый тип уловлен перехватом \(Object^\), он не разрушит созданный объект.  
  
 Когда функцию или улавливая неуправляемых исключений, не рекомендуется, используется параметр компилятора [\/EHsc](../build/reference/eh-exception-handling-model.md) вместо **\/EHs** или **\/EHa**.  
  
## См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)