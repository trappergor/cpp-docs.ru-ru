---
title: "Описатель класса хранения auto | Документация Майкрософт"
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
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
caps.latest.revision: 6
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
ms.openlocfilehash: a5c470eb63060b92e10ae3e31c2d6ccb6df22165
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="auto-storage-class-specifier"></a>Спецификатор классов хранения auto
Описатель класса хранения **auto** объявляет автоматическую переменную, то есть переменную с локальным временем существования. Переменная **auto** является видимой только в том блоке, в котором она объявлена. Объявления переменных **auto** могут содержать инициализаторы, как описано в статье [Инициализация](../c-language/initialization.md). Поскольку переменные с классом хранения **auto** не инициализируются автоматически, необходимо явно инициализировать их при объявлении или присвоить им начальные значения в операторах блока. Для неинициализированных переменных **auto** значения не определены. (Локальная переменная с классом хранения **auto** или **register** инициализируется заново каждый раз, когда она попадает в область видимости, если для нее указан инициализатор.)  
  
 Внутреннюю переменную **static** (статическую переменную с локальной областью видимости или областью видимости блока) можно инициализировать адресом любого внешнего элемента или элемента **static**, но не адресом элемента **auto**, поскольку адрес элемента **auto** не является константой.  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово auto](../cpp/auto-keyword.md)
