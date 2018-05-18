---
title: Описатель класса хранения static | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a7d61e39eb706721ddf936f88f5df02a6eddf96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="static-storage-class-specifier"></a>Спецификатор класса хранения static
Переменная, объявленная на внутреннем уровне с помощью описателя класса хранения **static**, имеет глобальное время существования, но является видимой только внутри блока, в котором она объявлена. Описатель **static** полезно использовать константных строках, потому что при этом снимается нагрузка частой инициализации в часто вызываемых функциях.  
  
## <a name="remarks"></a>Примечания  
Если переменная **static** не инициализирована явно, она инициализируется значением 0 по умолчанию. Внутри функции **static** выделяет хранилище и служит определением. Внутренние статические переменные представляют закрытое постоянное хранилище, видимое только одной функции.  
  
## <a name="see-also"></a>См. также  
[Классы хранения в C](c-storage-classes.md)  
[Storage classes (C++)](../cpp/storage-classes-cpp.md) (Классы хранения (C++))  