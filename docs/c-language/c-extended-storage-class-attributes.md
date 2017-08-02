---
title: "Расширенные атрибуты классов хранения в C | Документация Майкрософт"
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
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e79b08ebba48221e8666ced75875a68f06bf2df3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="c-extended-storage-class-attributes"></a>Расширенные атрибуты классов хранения в C
**Блок, относящийся только к системам Майкрософт**  
  
 Более актуальные сведения по этой теме вы найдете в [описании __declspec](../cpp/declspec.md) в справочнике по языку C++.  
  
 Расширенный синтаксис атрибутов упрощает и стандартизирует расширения для систем Microsoft в соответствии с правилами языка C. К атрибутам класса хранения, в которых используется расширенный синтаксис атрибутов, относятся: thread, naked, dllimport и dllexport.  
  
 Расширенный синтаксис атрибутов для указания информации о классе памяти использует ключевое слово , которое указывает, что экземпляр заданного типа должен храниться с соответствующим атрибутом класса хранения для систем Microsoft (thread, naked, dllimport или dllexport). Имеются и другие модификаторы класса хранения: ключевые слова static и extern. Однако эти ключевые слова входят в стандарт ANSI C, и как таковые они не используются с расширенным синтаксисом атрибутов.  
  
## <a name="syntax"></a>Синтаксис  
 *storage-class-specifier*:  
 `__declspec` (*extended-decl-modifier-seq*) /* Относится только к системам Microsoft \*/  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier* opt  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Модификаторы объявления разделяются пробелами. Обратите внимание, что *extended-decl-modifier-seq* может быть пустой, в этом случае ключевое слово __declspec игнорируется.  
  
 Атрибуты класса хранения thread, naked, dllimport и dllexport являются свойством только объявления данных или функции, к которому они применяются; они не переопределяют атрибуты типа самой функции. Атрибут thread влияет только на данные. Атрибут naked влияет только на функции. Атрибуты dllimport и dllexport влияют на функции и данные.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)
