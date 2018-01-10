---
title: "Предупреждение средств компоновщика LNK4099 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 364c2f9303707328ebf3bdf3284398e6d4f9f0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4099"></a>Предупреждение средств компоновщика LNK4099
PDB-ФАЙЛ «имя_файла» не найден «библиотека» или по «пути»; компоновка объекта выполняется как при отсутствии отладочных данных  
  
 Компоновщику не удается найти PDB-файл. Скопируйте его в каталог, содержащий `object/library`.  
  
 Чтобы найти имя PDB-файла, связанного с объектным файлом:  
  
1.  Извлеките объектный файл из библиотеки с [lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**.  
  
2.  Проверьте путь к PDB-файлу с **/section:.debug$ dumpbin T-/ RAWDATA** `objectname` **.obj**.  
  
 Также можно скомпилировать с [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), поэтому не нужно использовать, или удалите PDB-файл [/DEBUG](../../build/reference/debug-generate-debug-info.md) компоновщика, если у вас PDB-файлы для связываемых объектов.