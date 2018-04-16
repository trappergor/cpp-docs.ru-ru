---
title: грамматика выражения __based | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2cb2929fa595ad13746ea929217f41272a8189
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="based-grammar"></a>Грамматика выражения __based
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Базовая адресация полезна, когда требуется точный контроль над сегментом, в котором выделяются объекты (статические и динамические данные).  
  
 Единственной формой базовой адресации, допустимой в 32- и 64-разрядных компиляциях, является адресация на базе указателя, которая определяет тип, содержащий 32- или 64-разрядное смещение до 32- или 64-разрядной базы, или адресация на базе `void`.  
  
## <a name="grammar"></a>Грамматика  
 *на основе модификатор диапазона-*:  
 **__based (***базовое выражение***)**   
  
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