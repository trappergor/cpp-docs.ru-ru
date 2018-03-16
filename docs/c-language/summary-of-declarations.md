---
title: "Сводные сведения об объявлениях | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61dae4cf26f881014f0d98bbf30ebd10a360b10f
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="summary-of-declarations"></a>Общие сведения об объявлениях
`declaration`:  
 *declaration-specifiers attribute-seq* <sub>opt</sub> *init-declarator-list*<sub>opt</sub>**;**  
  
 /\* *attribute-seq* относится только к системам Microsoft */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers*<sub>opt</sub>  
  
 *type-specifier declaration-specifiers*<sub>opt</sub>  
  
 *type-qualifier declaration-specifiers*<sub>opt</sub>  
  
 *attribute-seq* :            /\* *attribute-seq* относится только к системам Microsoft \*/  
 *attribute attribute-seq* <sub>opt</sub>  
  
 *attribute* : one of      /* Microsoft Specific \*/  
 ||||  
|-|-|-|  
|[__asm](../assembler/inline/asm.md)|[__clrcall](../cpp/clrcall.md)|[__stdcall](../cpp/stdcall.md)|  
|[__based](../cpp/based-grammar.md)|[__fastcall](../cpp/fastcall.md)|[__thiscall](../cpp/thiscall.md)|  
|[__cdecl](../cpp/cdecl.md)|[__inline](../cpp/inline-functions-cpp.md)|[__vectorcall](../cpp/vectorcall.md)|  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* Для инициализации скалярных переменных \*/  
  
 *storage-class-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec (**  *extended-decl-modifier-seq*  **)** /* Относится только к системам Microsoft \*/  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 `__int8` /* Относится только к системам Microsoft \*/  
  
 `__int16` /* Относится только к системам Microsoft \*/  
  
 `__int32` /* Относится только к системам Microsoft \*/  
  
 `__int64` /* Относится только к системам Microsoft \*/  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *type-qualifier*:  
 **const**  
  
 `volatile`  
  
 `declarator`:  
 `pointer`<sub>opt</sub> *direct-declarator*  
  
 *direct-declarator*:  
 *identifier*  
  
 **(**  *declarator*  **)**  
  
 *direct-declarator*  **[**  *constant-expression* <sub>opt</sub>**]**  
  
 *direct-declarator*  **(**  *parameter-type-list*  **)** /* Декларатор нового стиля \*/  
  
 *direct-declarator*  **(**  *identifier-list*<sub>opt</sub>**)** /* Декларатор устаревшего стиля \*/  
  
 `pointer`:  
 **\*** *type-qualifier-list*<sub>opt</sub>  
  
 **\*** *type-qualifier-list*<sub>opt</sub>`pointer`  
  
 *parameter-type-list*:                           /\* Список параметров \*/  
 *parameter-list*  
  
 *parameter-list* **, ...**  
  
 *parameter-list*:  
 *parameter-declaration*  
  
 *parameter-list*  **,**  *parameter-declaration*  
  
 *type-qualifier-list*:  
 *type-qualifier*  
  
 *type-qualifier-list type-qualifier*  
  
 *enum-specifier*:  
 **enum**  *identifier*<sub>opt</sub>**{** *enumerator-list* **}**  
  
 **enum**  *identifier*  
  
 *enumerator-list*:  
 *enumerator*  
  
 *enumerator-list*  **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration-constant*  
  
 *enumeration-constant*  **=**  *constant-expression*  
  
 *enumeration-constant*:  
 *identifier*  
  
 *спецификатор-структуры-или-объединения*:  
 *struct-or-union identifier*<sub>opt</sub>**{** *struct-declaration-list* **}** *struct-or-union identifier*  
  
 *структура-или-объединение*:  
 **struct**  
  
 **объединение**  
  
 *список-объявлений-структуры*:  
 *объявление-структуры*  
  
 *список-объявлений-структуры объявление-структуры*  
  
 *объявление-структуры*:  
 *список-спецификаторов-и-квалификаторов список-деклараторов-структуры* **;**  
  
 *список-спецификаторов-и-квалификаторов*:  
 *type-specifier specifier-qualifier-list*<sub>opt</sub>  
  
 *type-qualifier specifier-qualifier-list*<sub>opt</sub>  
  
 *список-деклараторов-структуры*:  
 *struct-declarator struct-declarator-list*  **,**  *struct-declarator*  
  
 *декларатор-структуры*:  
 *declarator*  
  
 *type-specifier declarator*<sub>opt</sub>**:** *constant-expression*  
  
 *parameter-declaration*:  
 *declaration-specifiers declarator* /* Именованный декларатор \*/  
  
 *declaration-specifiers abstract-declarator*<sub>opt</sub>**/\*** Анонимный декларатор **\*/**  
  
 *identifier-list*: **/\*** Для декларатора устаревшего стиля **\* /**  
 *identifier*  
  
 *identifier-list*  **,**  *identifier*  
  
 *abstract-declarator*: **/\*** Используется с анонимными деклараторами **\*/**  
 *pointer*  
  
 `pointer`<sub>opt</sub>*direct-abstract-declarator*  
  
 *direct-abstract-declarator*:  
 **(**  *abstract-declarator*  **)**  
  
 *direct-abstract-declarator*<sub>opt</sub>**[** *constant-expression*<sub>opt</sub>**]**  
  
 *direct-abstract-declarator*<sub>opt</sub>**(** *parameter-type-list* <sub>opt</sub>**)**  
  
 *initializer*:  
 *assignment-expression*  
  
 **{**  *initializer-list*  **}** /* Для агрегатной инициализации \*/  
  
 **{**  *initializer-list*  **, }**  
  
 *initializer-list*:  
 *initializer*  
  
 *initializer-list*  **,**  *initializer*  
  
 *type-name*:  
 *specifier-qualifier-list abstract-declarator*<sub>opt</sub>  
  
 *typedef-name*:  
 *identifier*  
  
 *extended-decl-modifier-seq*:/\*    Относится только к системам Microsoft \*/  
 *extended-decl-modifier*<sub>opt</sub>  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier*:   /\* Относится только к системам Microsoft \*/  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
## <a name="see-also"></a>См. также  
 [Соглашения о вызовах](../cpp/calling-conventions.md)   
 [Грамматика структуры фразы](../c-language/phrase-structure-grammar.md)   
 [Устаревшие соглашения о вызовах](../cpp/obsolete-calling-conventions.md)