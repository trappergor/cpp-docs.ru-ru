---
title: "Предупреждение BSCMAKE BK4504 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: efe5cf36786171c4a663fb329efbc05b91065c7f
ms.lasthandoff: 02/24/2017

---
# <a name="bscmake-warning-bk4504"></a>Предупреждение BSCMAKE BK4504
файл содержит слишком много ссылок; дальнейшие ссылки из этого источника будут игнорироваться  
  
 CPP-файл содержит более 64 000 ссылки на символ. При обнаружении BSCMAKE 64 000 ссылки в файле игнорирует все дальнейшие ссылки.  
  
 Чтобы устранить проблему, разбить файл на два или несколько файлов, каждый из которых имеет не более 64 000 символьных ссылок или использовать `#pragma component(browser)` директивы препроцессора для ограничения символы, которые создаются для определенной ссылки. Дополнительные сведения см. в разделе [компонента](../../preprocessor/component.md).
