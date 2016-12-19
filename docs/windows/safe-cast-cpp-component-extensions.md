---
title: "safe_cast (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "safe_cast"
  - "safe_cast_cpp"
  - "stdcli::language::safe_cast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast - ключевое слово [C++]"
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# safe_cast (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В случае успешного выполнения операция `safe_cast` возвращает указанное выражение как указанный тип; в противном случае вызывается исключение `InvalidCastException`.  
  
## Все среды выполнения  
 \(Отсутствуют комментарии для этой функции языка, которая применяется во всех средах выполнения.\)  
  
### Синтаксис  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Параметры  
  
### Примечания  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Параметр `safe_cast` позволяет изменить тип указанного выражения.  В ситуациях, где вы полностью рассчитываете на возможность преобразования переменной или параметра в определенный тип, можно использовать safe\_cast без блока try\-catch для обнаружения ошибок программирования во время разработки.  Дополнительные сведения см. в разделе [Приведение \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).  
  
### Синтаксис  
  
```cpp  
  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Параметры  
 *type\-id*  
 Тип, в который следует преобразовать *выражение*.  Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.  
  
 *expression*  
 Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.  
  
### Примечания  
 Параметр `safe_cast` вызывает исключение  `InvalidCastException`, если не может преобразовать выражение *expression* в тип, заданный параметром *type\-id*.  Для перехвата `InvalidCastException` укажите параметр компилятора [Параметр \/EH \(модель обработки исключений\)](../build/reference/eh-exception-handling-model.md) и используйте оператор try\-catch.  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
### Примеры  
 **Пример**  
  
 В следующем примере кода показано, как использовать `safe_cast` с [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **Вывод**  
  
  **Перехвачено ожидаемое исключение: InvalidCastException**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Параметр `safe_cast` позволяет изменить тип выражения и создать проверяемый код MSIL.  
  
### Синтаксис  
  
```cpp  
  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### Параметры  
 *type\-id*  
 Дескриптор ссылки или типа значения, тип значения или отслеживаемая ссылка на ссылку или тип значения.  
  
 *expression*  
 Выражение, которое оценивается в дескрипторе ссылки или типа значения, типе значения или отслеживаемой ссылке на ссылку или тип значения.  
  
### Примечания  
 Выражение `safe_cast<`*type\-id*`>(`*expression*`)` преобразует выражение операнда в объект с типом type\-id.  
  
 Компилятор будет принимать [static\_cast](../cpp/static-cast-operator.md) в большинстве мест, где будет принимать `safe_cast`.  Однако `safe_cast` гарантированно создает проверяемый код MSIL, тогда как `static_cast` может создать непроверяемый MSIL.  Дополнительные сведения о проверяемом коде см. в разделах [Чистый и проверяемый код](../dotnet/pure-and-verifiable-code-cpp-cli.md) и [Peverify.exe \(PEVerify Tool\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md).  
  
 Как и `static_cast`, `safe_cast` вызывает заданные пользователем преобразования.  
  
 Дополнительные сведения о приведениях см. в разделе [Операторы приведения](../cpp/casting-operators.md).  
  
 `safe_cast` не применяет **const\_cast**  \(отвергает **const**\).  
  
 `safe_cast` находится в пространстве имен CLI.  Дополнительные сведения см. в разделе [Пространства имен Platform, default и cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Дополнительные сведения о **safe\_cast** см. в следующих разделах.  
  
-   [Приведение в стиле C с использованием параметра \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [Практическое руководство. Использование safe\_cast в C\+\+\/CLI](../Topic/How%20to:%20Use%20safe_cast%20in%20C++-CLI.md)  
  
-   [Практическое руководство. Нисходящее приведение с помощью safe\_cast](../misc/how-to-downcast-with-safe-cast.md)  
  
-   [Практическое руководство. Использование safe\_cast и универсальных типов](../misc/how-to-use-safe-cast-and-generic-types.md)  
  
-   [Практическое руководство. Использование safe\_cast и определенных пользователем преобразований](../misc/how-to-use-safe-cast-and-user-defined-conversions.md)  
  
-   [Практическое руководство. Использование safe\_cast и упаковки\-преобразования](../Topic/How%20to:%20Use%20safe_cast%20and%20Boxing.md)  
  
-   [Практическое руководство. Использование safe\_cast и распаковки\-преобразования](../misc/how-to-use-safe-cast-and-unboxing.md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 Пример, когда компилятор не будет принимать `static_cast`, но будет принимать `safe_cast`, —приведения между несвязанными типами интерфейса.  При использовании `safe_cast` компилятор не будет выдавать ошибку преобразования и будет выполнять проверку во время выполнения, чтобы увидеть, возможно ли приведение.  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **Вывод**  
  
  **Перехвачено ожидаемое исключение.**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)