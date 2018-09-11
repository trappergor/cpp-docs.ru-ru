---
title: Основные принципы использования управляемых исключений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ad3b00367be086bfe6e011b0d3aa7b93805eb103
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202050"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Основные принципы использования управляемых исключений
В этом разделе рассматривается обработка исключений в управляемых приложениях. То есть приложение, которое компилируется с **/CLR** параметр компилятора.  
  
## <a name="in-this-topic"></a>Содержание раздела  
  
-   [Создание исключений в/CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Блоки Try/Catch для расширения среды CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>Примечания  
 Если компиляция выполняется с **/CLR** параметр, можно обрабатывать исключения среды CLR, а также стандартный [обработки исключений C++](../cpp/cpp-exception-handling.md) и [структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md) (SEH). Исключения среды CLR — это любое исключение, вызванное управляемый тип. [System::Exception](https://msdn.microsoft.com/library/system.exception.aspx) класс предоставляет множество полезных методов для обработки исключения CLR и рекомендуется в качестве базового класса для классов исключений, определяемых пользователем.  
  
 Перехват исключения типов, производных от интерфейса не поддерживается в **/CLR**. Кроме того среда CLR позволяет перехватывать исключения переполнения стека; процесс будет прерван исключение переполнения стека.  
  
 Дополнительные сведения о различиях в обработке исключений в управляемых и неуправляемых приложений см. в разделе [различия в исключение обработки поведение в управляемых расширений для C++](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> Создание исключений в/CLR  
 Выражение throw C++ расширяется для throw дескриптор для типа CLR. В следующем примере создается пользовательский тип исключения и затем создает экземпляр этого типа:  
  
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
  
 Тип значения должны упаковываться перед вызываемом:  
  
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
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Блоки Try/Catch для расширения среды CLR  
 Же **попробуйте**/**catch** блочной структуры можно использовать для перехвата CLR и собственных исключений:  
  
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
 Очистка происходит для любых объектов C++ с деструкторами, которые могут быть в стеке времени выполнения, функция создает исключение и функции обработки. Так как типы CLR выделяются в куче, очистки не применяется к ним.  
  
 Ниже приведен порядок событий для созданного исключения:  
  
1.  Среда выполнения выполняет обход стека, соответствующие catch предложения, или в случае SEH, за исключением фильтр для SEH, чтобы перехватить исключение. Предложения catch производится поиск сначала в лексическом порядке, а затем динамически вниз стека вызовов.  
  
2.  После обнаружения правильный обработчик стек освобождается для этой точки. Для каждого вызова функции в стеке будут уничтожены его локальных объектов и __finally выполняются блоки, от большинства вложенных наружу.  
  
3.  После стек освобождается, выполняется в предложении catch.  
  
### <a name="catching-unmanaged-types"></a>Перехват неуправляемых типов  
 При возникновении неуправляемый объект типа, он упаковывается с исключением типа [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx). При поиске соответствующего **catch** предложение, существуют две возможности.  
  
-   Если в собственный тип C++, расшифровывается и по сравнению с обнаружен тип исключения. Это сравнение позволяет собственный тип C++ оказалось обычным способом.  
  
-   Тем не менее если **catch** конструкции типа **SEHException** или любой из его базовых классов проверяется, во-первых, предложение будет перехватывать исключение. Таким образом необходимо поместить все предложения catch, которые захватывают собственных типов C++ во-первых, перед любой catch предложения типов CLR.  
  
 Обратите внимание на следующие условия.  
  
```  
catch(Object^)  
```  
  
 и  
  
```  
catch(...)  
```  
  
 Оба перехватывает любого созданного типа, включая исключения SEH.  
  
 Если catch(Object^) перехвачено неуправляемого типа, он не будет уничтожена созданный объект.  
  
 Когда создание или перехват неуправляемые исключения, мы рекомендуем использовать [/EHsc](../build/reference/eh-exception-handling-model.md) параметр компилятора вместо **/EHs** или **/EHa**.  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)