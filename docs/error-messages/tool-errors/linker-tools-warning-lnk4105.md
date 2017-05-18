---
title: "Предупреждение средств компоновщика LNK4105 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f7d0a4e956ec78dfdac7f54895405025bdb11559
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4105"></a>Предупреждение средств компоновщика LNK4105
не указан аргумент параметра «параметр»; параметр игнорируется  
  
 Это предупреждение возникает только при [/LIBPATH](../../build/reference/libpath-additional-libpath.md) был установлен. Если каталог не указан этот параметр, компоновщик игнорирует параметр и создает это предупреждающее сообщение.  
  
 Если необходимо переопределить существующие настройки библиотеки среды, удалите параметр/LIBPATH из командной строки компоновщика. Если вы хотите использовать поиска альтернативный путь для библиотек, укажите альтернативный путь после параметра/LIBPATH.  
  
## <a name="example"></a>Пример  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 компоновщиком для поиска необходимых библиотек в `c:\filepath\lib` перед поиском в расположение по умолчанию.
