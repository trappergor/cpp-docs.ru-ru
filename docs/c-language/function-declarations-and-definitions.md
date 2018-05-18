---
title: Объявления и определения функций | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 704e8defa8aac640ce5011e5789d4af36380b7a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="function-declarations-and-definitions"></a>Объявления и определения функций
Прототипы функций устанавливают имя функции, тип возвращаемого ею значения, а также тип и число ее формальных параметров. Определение функции содержит тело функции.  
  
## <a name="remarks"></a>Примечания  
 Объявления функции и переменных могут находиться внутри или вне определения функции. Считается, что любое объявление, сделанное внутри определения функции, находится на "внутреннем", или "локальном", уровне, а объявление, расположенное вне всех определений функций, находится на внешнем, глобальном уровне или на уровне области видимости файла. Определения переменных, подобно объявлениям, могут находиться на внутреннем (в определении функции) или внешнем (вне всех определений функций) уровне. Определения функций всегда находятся на внешнем уровне. Подробнее определения функций рассматриваются в статье [Определения функций](../c-language/c-function-definitions.md). Прототипы функций описаны в статье [Прототипы функций](../c-language/function-prototypes.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)