---
title: Предупреждение средств компоновщика LNK4099 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22764705b35b2e882c5a03e819c9812d084dc118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300817"
---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099
PDB-ФАЙЛ «имя_файла» не найден «библиотека» или по «пути»; компоновка объекта выполняется как при отсутствии отладочных данных  
  
 Компоновщику не удается найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.  
  
 Чтобы найти имя PDB-файла, связанного с объектным файлом:  
  
1.  Извлеките объектный файл из библиотеки с [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.  
  
2.  Проверьте путь к PDB-файлу с **/section:.debug$ dumpbin T-/ RAWDATA** `objectname` **.obj**.  
  
 Также можно скомпилировать с [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), поэтому не нужно использовать, или удалите PDB-файл [/DEBUG](../../build/reference/debug-generate-debug-info.md) компоновщика, если у вас PDB-файлы для связываемых объектов.