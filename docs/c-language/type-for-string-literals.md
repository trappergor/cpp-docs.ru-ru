---
title: "Тип для строковых литералов | Документация Майкрософт"
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
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2342777bfd2b1a039e68766e8dfe00ac2fa2f932
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-for-string-literals"></a>Тип для строковых литералов
Строковые литералы имеют тип массива `char` (т. е., **char[ ]**). (Строки расширенных символов имеют тип массива `wchar_t` (т. е., **wchar_t []**).) Это означает, что строка является массивом с элементами типа `char`. Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.  
  
## <a name="see-also"></a>См. также  
 [Строковые литералы в C](../c-language/c-string-literals.md)