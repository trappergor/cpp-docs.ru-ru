---
title: "__declspec | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b29b6243611f1ca59a579869469c803d3735f9df
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Расширенный синтаксис атрибутов для указания данных класса памяти использует ключевое слово `__declspec`, которое указывает, что экземпляр заданного типа должен хранится с перечисленным ниже атрибутом класса хранения для систем Microsoft. Примеры других модификаторов класса хранения включают ключевые слова `static` и `extern`. Однако эти ключевые слова — часть спецификации ANSI языков C и C++, и как таковые они не описаны расширенным синтаксисом атрибутов. Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языков C и С++.  
  
## <a name="grammar"></a>Грамматика  
 *спецификатор decl*:  
 `__declspec (`  *расширенные последовательность модификаторов объявления*  `)`  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier*opt  
  
 *модификатор расширенного объявления расширенных последовательность модификаторов объявления*  
  
 *extended-decl-modifier*:  
 `align(` *#* `)`  
  
 `allocate("`*segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*segname*`")`  
  
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
  
 `property(`{`get=`*get_func_name*&#124;`,put=` *put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 Пробел отделяет последовательность модификаторов объявления. Примеры приведены в дальнейших разделах.  
  
 Эти атрибуты класса хранения Майкрософт поддерживаются грамматикой расширенный атрибут: [выравнивание](../cpp/align-cpp.md), [выделить](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [устаревшими](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [процесс](../cpp/process.md), [ограничить](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), и [поток](../cpp/thread.md). Оно также поддерживает следующие атрибуты COM-объекта: [свойство](../cpp/property-cpp.md) и [uuid](../cpp/uuid-cpp.md).  
  
 Атрибуты класса хранения `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` и `uuid` — это свойства исключительно объявления объекта или функции, к которым они применяются. Атрибут `thread` влияет только на данные и объекты. Атрибут `naked` влияет только на функции. Атрибуты `dllimport` и `dllexport` влияют на функции, данные и объекты. Атрибуты `property`, `selectany` и `uuid` влияют на COM-объекты.  
  
 Ключевые слова `__declspec` необходимо поместить в начале простого объявления. Компилятор игнорирует без предупреждения все ключевые слова `__declspec`, находящиеся после * или &, а также перед идентификатором переменной в объявлении.  
  
 Атрибут `__declspec`, указанный в начале объявления пользовательского типа, относится к переменной этого типа. Например:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 В этом случае атрибут применяется к `varX`. Атрибут `__declspec`, помещенный после ключевого слова `class` или `struct`, применяется к пользовательскому типу. Например:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 В этом случае атрибут применяется к `X`.  
  
 Ниже приводятся общие рекомендации для использования атрибута `__declspec` для простых объявлений.  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 *Decl-specifier-seq* должен содержать, помимо прочего, базовый тип (например `int`, `float`, `typedef`, или имя класса), класс хранения (например `static`, `extern`), или `__declspec`расширения. *Список деклараторов* должен содержать, помимо прочего, часть объявления указателя. Пример:  
  
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
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)
