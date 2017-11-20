---
title: "Классы хранения в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, lifetime
- storage classes
- lifetime, variables
- specifiers, storage class
- storage class specifiers, C storage classes
- storage duration
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: afec3ea0d88ff7ede9c498a270e2806a4ceb79e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-storage-classes"></a>Классы хранения в C
"Класс хранения" переменной определяет время существования элемента: глобальное или локальное. В языке С это время существования называется "статическое" или "автоматическое". Элемент с глобальным временем существования присутствует и имеет значение на протяжении всего исполнения программы. Все функции имеют глобальное время существования.  
  
 Автоматические переменные или переменные с локальным временем существования получают новое место хранения всякий раз, когда контроль исполнения переходит к блоку, в котором они определены. Когда выполнение возвращается, переменные более не имеют понятных значений.  
  
 C предоставляет следующие описатели класса хранения:  
  
## <a name="syntax"></a>Синтаксис  
 *storage-class-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec** (*extended-decl-modifier-seq*) /* Относится только к системам Microsoft \*/  
  
 За исключением `__declspec`, в составе *declaration-specifier* в объявлении можно использовать только один описатель *storage-class-specifier*. Если нет спецификации класса хранения, объявления в блоке создают автоматические объекты.  
  
 Элементы, объявленные с описателем **auto** или **register**, имеют локальное время существования. Элементы, объявленные с описателем **static** или `extern`, имеют глобальное время существования.  
  
 Поскольку `typedef` и `__declspec` семантически отличаются от других четырех терминалов *storage-class-specifier*, они обсуждаются отдельно. Подробные сведения о `typedef` есть в статье [Объявления Typedef](../c-language/typedef-declarations.md). Подробные сведения о `__declspec` см. в статье [Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md).  
  
 Размещение объявлений переменных и функций в файлах исходного кода также влияет на класс хранения и видимость. Объявления вне определений функций отображаются на внешнем уровне. Объявления в составе определений функций отображаются на внутреннем уровне.  
  
 Точное значение каждого определителя класса хранения зависит от двух факторов:  
  
-   уровня отображения объявления (внешний или внутренний)  
  
-   типа объявляемого элемента (переменная или функция)  
  
 В статьях [Описатели классов хранения для объявлений внешнего уровня](../c-language/storage-class-specifiers-for-external-level-declarations.md) и [Описатели классов хранения для объявлений внутреннего уровня](../c-language/storage-class-specifiers-for-internal-level-declarations.md) описаны терминалы *storage-class-specifier* для каждого типа объявлений и поведение по умолчанию в случае отсутствия *storage-class-specifier* в декларации переменной. Статья [Описатели классов хранения с объявлениями функций](../c-language/storage-class-specifiers-with-function-declarations.md) поможет разобраться с описателями storage-class, используемыми с функциями.  
  
## <a name="see-also"></a>См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)