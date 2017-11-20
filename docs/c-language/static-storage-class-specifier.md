---
title: "Описатель класса хранения static | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a51dfc10ac0ae05a67a280b4b76c2c92eb57a0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="static-storage-class-specifier"></a>Спецификатор класса хранения static
Переменная, объявленная на внутреннем уровне с помощью описателя класса хранения **static**, имеет глобальное время существования, но является видимой только внутри блока, в котором она объявлена. Описатель **static** полезно использовать константных строках, потому что при этом снимается нагрузка частой инициализации в часто вызываемых функциях.  
  
## <a name="remarks"></a>Примечания  
Если переменная **static** не инициализирована явно, она инициализируется значением 0 по умолчанию. Внутри функции **static** выделяет хранилище и служит определением. Внутренние статические переменные представляют закрытое постоянное хранилище, видимое только одной функции.  
  
## <a name="see-also"></a>См. также  
[Классы хранения в C](c-storage-classes.md)  
[Storage classes (C++)](../cpp/storage-classes-cpp.md) (Классы хранения (C++))  