---
title: "грамматика выражения __based | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
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
ms.openlocfilehash: 427906751c57b8b5f0c46479e8481394fa20f56c
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="based-grammar"></a>Грамматика выражения __based
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Базовая адресация полезна, когда требуется точный контроль над сегментом, в котором выделяются объекты (статические и динамические данные).  
  
 Единственной формой базовой адресации, допустимой в 32- и 64-разрядных компиляциях, является адресация на базе указателя, которая определяет тип, содержащий 32- или 64-разрядное смещение до 32- или 64-разрядной базы, или адресация на базе `void`.  
  
## <a name="grammar"></a>Грамматика  
 *на основе модификатор диапазона-*:  
 **__based (***базовое выражение***)    **  
  
 *базовое выражение*:  
 *based-variablebased-abstract-declaratorsegment-namesegment-CAST*  
  
 *на основе переменной*:  
 *identifier*  
  
 *на основе абстрактный декларатор*:  
 *Абстрактный декларатор*  
  
 *базовый тип*:  
 *Имя типа*  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Относительные указатели](../cpp/based-pointers-cpp.md)
