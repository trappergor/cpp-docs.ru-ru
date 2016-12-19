---
title: "__declspec | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__declspec_cpp"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++]"
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __declspec
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Расширенный синтаксис атрибутов для указания данных класса памяти использует ключевое слово `__declspec`, которое указывает, что экземпляр заданного типа должен хранится с перечисленным ниже атрибутом класса хранения для систем Microsoft.  Примеры других модификаторов класса хранения включают ключевые слова `static` и `extern`.  Однако эти ключевые слова — часть спецификации ANSI языков C и C\+\+, и как таковые они не описаны расширенным синтаксисом атрибутов.  Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С\+\+.  
  
## Грамматика  
 *decl\-specifier*:  
 `__declspec (`  *extended\-decl\-modifier\-seq*  `)`  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier* необ  
  
 *extended\-decl\-modifier extended\-decl\-modifier\-seq*  
  
 *extended\-decl\-modifier*:  
 `align(` *\#* `)`  
  
 `allocate("` *segname* `")`  
  
 `appdomain`  
  
 `code_seg("` *segname* `")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get\_func\_name*&#124;`,put=`*put\_func\_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("` *ComObjectGUID* `")`  
  
 Пробел отделяет последовательность модификаторов объявления.  Примеры приведены в дальнейших разделах.  
  
 Расширенная форма атрибутов поддерживает следующие атрибуты классов памяти для систем Microsoft: [align](../cpp/align-cpp.md), [allocate](../Topic/allocate.md), [appdomain](../Topic/appdomain.md), [code\_seg](../cpp/code-seg-declspec.md), [deprecated](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../Topic/naked%20\(C++\).md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../Topic/nothrow%20\(C++\).md), [novtable](../cpp/novtable.md), [process](../cpp/process.md), [restrict](../cpp/restrict.md), [safebuffers](../Topic/safebuffers.md), [selectany](../cpp/selectany.md) и [thread](../cpp/thread.md).  Она также поддерживает следующие атрибуты COM\-объекта: [property](../cpp/property-cpp.md) и [uuid](../cpp/uuid-cpp.md).  
  
 Атрибуты класса хранения `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` и `uuid` — это свойства исключительно объявления объекта или функции, к которым они применяются.  Атрибут `thread` влияет только на данные и объекты.  Атрибут `naked` влияет только на функции.  Атрибуты `dllimport` и `dllexport` влияют на функции, данные и объекты.  Атрибуты `property`, `selectany` и `uuid` влияют на COM\-объекты.  
  
 Ключевые слова `__declspec` необходимо поместить в начале простого объявления.  Компилятор игнорирует без предупреждения все ключевые слова `__declspec`, находящиеся после \* или &, а также перед идентификатором переменной в объявлении.  
  
 Атрибут `__declspec`, указанный в начале объявления пользовательского типа, относится к переменной этого типа.  Например:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 В этом случае атрибут применяется к `varX`.  Атрибут `__declspec`, помещенный после ключевого слова `class` или `struct`, применяется к пользовательскому типу.  Например:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 В этом случае атрибут применяется к `X`.  
  
 Ниже приводятся общие рекомендации для использования атрибута `__declspec` для простых объявлений.  
  
```  
  
decl-specifier-seq declarator-list;  
```  
  
 *decl\-specifier\-seq* должно содержать, помимо прочего, базовый тип \(например,  `int`, `float`, `typedef` или имя класса\), класс хранения \(например  `static`, `extern`\) или расширение `__declspec`.  *init\-declarator\-list* должно содержать, помимо прочего, часть указателя объявлений.  Например:  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 В следующем примере кода объявлена целочисленная локальная переменная потока и инициализирована с использованием следующего значения:  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)