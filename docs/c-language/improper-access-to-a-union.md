---
title: "Неправильный доступ к объединению | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 54eeffebcc20846666c6ebb6a2951f8d55a5b8c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="improper-access-to-a-union"></a>Неправильный доступ к объединению
**ANSI 3.3.2.3** Доступ к члену объекта объединения через члена другого типа  
  
 Если объявляется объединение двух типов и сохраняется одно значение, но для доступа к объединению используется другой тип, результаты будут ненадежными.  
  
 Например, объявлено объединение **float** и `int`. Сохраняется значение **float**, но программа позднее использует это значение как `int`. Полученное значение будет зависеть от типа внутреннего хранилища для значений **float**. Целочисленное значение будет ненадежным.  
  
## <a name="see-also"></a>См. также  
 [Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)