---
title: "Неустранимая ошибка C1852 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f3e2b190ed3ec30c429bded2b6b695e1838cd078
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1852"></a>Неустранимая ошибка C1852
"имя_файла" не является допустимым файлом предкомпилированного заголовка  
  
 Файл не является предкомпилированным заголовком.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указан недопустимый файл с **/Yu** или **#pragma hdrstop**.  
  
2.  Если не указано иное, компилятор предполагает расширение файла PCH.
