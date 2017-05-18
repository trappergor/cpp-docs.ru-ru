---
title: "Предупреждение средств компоновщика LNK4099 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: 9
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
ms.openlocfilehash: 7de3ce64ca3a9c5a5b0738888b6c83b4694bd895
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099
PDB-ФАЙЛ «ИмяФайла» не найден в «библиотека» или по «пути»; компоновка объекта без отладочной информации  
  
 Компоновщику не удается найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.  
  
 Чтобы найти имя PDB-файла, связанного с объектным файлом:  
  
1.  Извлеките объектный файл из библиотеки с [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.  
  
2.  Проверьте путь к PDB-файл с **/section:.debug$ dumpbin T-/ RAWDATA** `objectname` **.obj**.  
  
 Также можно скомпилировать с [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), поэтому pdb не требуется использовать или удалить [/DEBUG](../../build/reference/debug-generate-debug-info.md) параметр компоновщика, если нет PDB-файлы для связываемых объектов.
