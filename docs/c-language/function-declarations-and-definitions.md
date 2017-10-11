---
title: "Объявления и определения функций | Документация Майкрософт"
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
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: ea315c065e6f76215939bc4ccd70bcc907361ff4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="function-declarations-and-definitions"></a>Объявления и определения функций
Прототипы функций устанавливают имя функции, тип возвращаемого ею значения, а также тип и число ее формальных параметров. Определение функции содержит тело функции.  
  
## <a name="remarks"></a>Примечания  
 Объявления функции и переменных могут находиться внутри или вне определения функции. Считается, что любое объявление, сделанное внутри определения функции, находится на "внутреннем", или "локальном", уровне, а объявление, расположенное вне всех определений функций, находится на внешнем, глобальном уровне или на уровне области видимости файла. Определения переменных, подобно объявлениям, могут находиться на внутреннем (в определении функции) или внешнем (вне всех определений функций) уровне. Определения функций всегда находятся на внешнем уровне. Подробнее определения функций рассматриваются в статье [Определения функций](../c-language/c-function-definitions.md). Прототипы функций описаны в статье [Прототипы функций](../c-language/function-prototypes.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)
