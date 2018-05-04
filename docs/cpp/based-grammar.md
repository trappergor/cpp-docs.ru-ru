---
title: грамматика выражения __based | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20e1c14cd7add01f8583c24541987b2980da794a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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