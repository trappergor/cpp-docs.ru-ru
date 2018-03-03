---
title: "Основные принципы использования управляемых исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5e2faf56f050610e6c98ff82cdca10333a54fd93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Основные принципы использования управляемых исключений
В этом разделе рассматривается обработка исключений в управляемых приложениях. То есть приложение, которое скомпилировано с **/CLR** параметр компилятора.  
  
## <a name="in-this-topic"></a>Содержание раздела  
  
-   [Создание исключений в/CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Блоки Try/Catch для расширения среды CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>Примечания  
 Если компиляция выполняется с **/CLR** параметр, можно обрабатывать исключения среды CLR, а также стандартные [обработка исключений с ++](../cpp/cpp-exception-handling.md) и [структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md) (SEH). Исключение CLR является любое исключение, вызванное управляемого типа. [System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) класс предоставляет много полезных методов обработки исключений CLR и рекомендуется в качестве базового класса для исключений, определяемых пользователем классов.  
  
 Перехват исключения типам, производным от интерфейса не поддерживается в **/CLR**. Кроме того среда не позволяют перехватывать исключения переполнения стека; исключение переполнения стека, завершает процесс.  
  
 Дополнительные сведения о различиях в обработке исключений в управляемых и неуправляемых приложений см. в разделе [различия в исключение обработки поведение в управляемых расширениях для C++](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>Создание исключений в/CLR  
 Выражение throw C++ расширяется для вызова дескриптор к типу CLR. В следующем примере создается тип пользовательское исключение и затем создает экземпляр этого типа:  
  
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
  
 Тип значения должны быть упакованы перед вызываемом:  
  
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
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Блоки Try/Catch для расширения среды CLR  
 Соответствует **повторите**/**перехватывать** блок структуры можно использовать для перехвата CLR и исходные исключения:  
  
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
  
### <a name="output"></a>Вывод  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### <a name="order-of-unwinding-for-c-objects"></a>Порядок очистки для объектов C++  
 Очистка происходит для любых объектов C++ с деструкторами, которые могут быть включены между функция создает исключение и функцию обработки стека во время выполнения. Так как типы CLR размещенных в куче, очистки не применяется к ним.  
  
 Ниже приведен порядок событий исключения:  
  
1.  Среда выполнения выполняет обход стека поиска для предложения соответствующие catch или в случае SEH, за исключением фильтр для SEH, чтобы перехватить исключение. Предложения catch сначала производится в лексическом порядке, а затем динамически вниз стека вызовов.  
  
2.  После обнаружения правильный обработчик стек освобождается до этого момента. Для каждого вызова функции в стеке будут уничтожены его локальных объектов и __finally выполнены все блоки большинства вложенных наружу.  
  
3.  После стек освобождается, выполняется предложение catch.  
  
### <a name="catching-unmanaged-types"></a>Перехват неуправляемые типы  
 При возникновении неуправляемый объект типа, он заключается в оболочку с исключение типа [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx). При поиске соответствующего **перехватывать** предложение, есть две возможности.  
  
-   При обнаружении собственный тип C++ исключение без оболочки и по сравнению с обнаружен тип. Это сравнение позволяет собственный тип C++ перехватывать обычным способом.  
  
-   Однако если **перехватывать** предложения типа **SEHException** или любого из его базовых классов сначала проверяется, предложение будет перехватывать исключение. Таким образом необходимо поместить все предложения catch, которые захватывают собственные типы C++ сначала перед любой перехватывать предложений типов среды CLR.  
  
 Обратите внимание на следующие условия.  
  
```  
catch(Object^)  
```  
  
 и  
  
```  
catch(...)  
```  
  
 Оба перехватывает любого созданного типа, включая исключения SEH.  
  
 Если неуправляемый тип перехвачено catch(Object^), он не приведет к удалению созданный объект.  
  
 Когда происходить создание или перехват неуправляемые исключения, мы рекомендуем использовать [/EHsc](../build/reference/eh-exception-handling-model.md) параметр компилятора вместо **/EHs** или **/EHa**.  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)