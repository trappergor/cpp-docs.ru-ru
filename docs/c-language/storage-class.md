---
title: "Класс хранения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d2a6e5026e71d993675fff3674af3fe6d2f9be96
ms.lasthandoff: 02/24/2017

---
# <a name="storage-class"></a>Класс хранения
Спецификатор класса хранения в определении функции предоставляет ей класс хранения `extern` или **static**.  
  
## <a name="syntax"></a>Синтаксис  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* Относится только к системам Microsoft */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*: /\* Для определений функции \*/  
 **extern**  
  
 **static**  
  
 Если определение функции не содержит *storage-class-specifier*, по умолчанию устанавливается класс хранения `extern`. Функцию можно явно объявить как `extern`, но это необязательно.  
  
 Если объявление функции содержит *storage-class-specifier* `extern`, идентификатор имеет ту же компоновку, что и любое видимое объявление идентификатора с областью видимости файла. Если видимого объявления с областью видимости файла нет, идентификатор имеет внешнюю компоновку. Если идентификатор содержит область видимости файла и не содержит *storage-class-specifier*, он имеет внешнюю компоновку. Внешняя компоновка означает, что каждый экземпляр идентификатора определяет один и тот же объект или функцию. Дополнительные сведения о компоновке и области видимости файла см. в статье [Lifetime, Scope, Visibility, and Linkage](../c-language/lifetime-scope-visibility-and-linkage.md) (Время существования, область, видимость и компоновка).  
  
 Объявления функций в области видимости блока со спецификатором класса хранения, отличным от `extern`, приводят к ошибкам.  
  
 Функция с классом хранения **static** видна только в исходном файле, в котором она определена. Все остальные функции видны во всех исходных файлах программы независимо от того, явно или неявно им предоставлен класс хранения `extern`. Если требуется класс хранения **static**, он должен быть объявлен в первом экземпляре объявления функции (при его наличии) и в определении функции.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 При включенных расширениях Майкрософт функции, первоначально объявленной без класса хранения (или с классом хранения `extern`), предоставляется класс хранения **static**, если определение этой функции находится в том же исходном файле и в нем явно указан класс хранения **static**.  
  
 При компиляции с параметром компилятора /Ze функции, объявленные внутри блока с помощью ключевого слова `extern`, имеют глобальную видимость. При компиляции с параметром /Za это не так. Если необходимо учитывать переносимость исходного кода, не следует полагаться на эту возможность.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Определения функций в C](../c-language/c-function-definitions.md)
