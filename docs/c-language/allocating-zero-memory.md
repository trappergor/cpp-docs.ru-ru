---
title: "Выделение нулевой памяти (C) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9708f8939ff32f9320e7c8e803753e801ce9448f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-zero-memory"></a>Выделение обнуленной памяти
**ANSI 4.10.3** Поведение функции `calloc`, `malloc` или `realloc`, если запрошенный размер равен нулю  
  
 Функции `calloc`, `malloc` и `realloc` принимают в качестве аргумента нуль. Фактическая память не распределяется, однако возвращается допустимый указатель, и блок памяти можно изменить впоследствии путем перераспределения.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)