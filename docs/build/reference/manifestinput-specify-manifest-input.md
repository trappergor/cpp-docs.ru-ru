---
title: -MANIFESTINPUT (задание входных данных манифеста) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1b5ed266f1b8929deee3ffb60a10b18b7604afc
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572775"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (задание входных данных манифеста)
Задает входной файл манифеста для включения в манифест, внедренный в изображение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/MANIFESTINPUT:filename  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Файл манифеста для включения во встроенный манифест.  
  
## <a name="remarks"></a>Примечания  
 **/MANIFESTINPUT** указывает путь к входного файла для создания внедренного манифеста в исполняемом образе. При наличии нескольких входных файлов манифеста, используйте параметр несколько раз — один раз для каждого входного файла. Входные файлы манифеста объединяются для создания внедренного манифеста. Этот параметр требует **/MANIFEST: ВНЕДРЕНИЕ** параметр.  
  
 Этот параметр нельзя установить непосредственно в Visual Studio. Вместо этого используйте **дополнительные файлы манифеста** свойства проекта, чтобы указать дополнительные файлы манифеста для включения. Дополнительные сведения см. в разделе [входные и выходные данные, инструмент манифеста, свойства конфигурации, \<имя_проекта > "диалогового окна" страницы свойств "](../../ide/input-and-output-manifest-tool.md).  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)