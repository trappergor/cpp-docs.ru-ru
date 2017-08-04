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
ms.openlocfilehash: da1be05d6b5fe77113199c73101115e4e221cf09
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="function-declarations-and-definitions"></a>Объявления и определения функций
Прототипы функций устанавливают имя функции, тип возвращаемого ею значения, а также тип и число ее формальных параметров. Определение функции содержит тело функции.  
  
## <a name="remarks"></a>Примечания  
 Объявления функции и переменных могут находиться внутри или вне определения функции. Считается, что любое объявление, сделанное внутри определения функции, находится на "внутреннем", или "локальном", уровне, а объявление, расположенное вне всех определений функций, находится на внешнем, глобальном уровне или на уровне области видимости файла. Определения переменных, подобно объявлениям, могут находиться на внутреннем (в определении функции) или внешнем (вне всех определений функций) уровне. Определения функций всегда находятся на внешнем уровне. Подробнее определения функций рассматриваются в статье [Определения функций](../c-language/c-function-definitions.md). Прототипы функций описаны в статье [Прототипы функций](../c-language/function-prototypes.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)
