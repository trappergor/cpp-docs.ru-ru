---
title: -MANIFESTINPUT (задание входных данных манифеста) | Документы Microsoft
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
ms.openlocfilehash: eecf1740855c2feef0d7cac4bbcc85ad95eade6f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (задание входных данных манифеста)
Задает входной файл манифеста для включения в манифесте, внедренных в изображение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/MANIFESTINPUT:filename  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Файл манифеста для включения в внедренный манифест.  
  
## <a name="remarks"></a>Примечания  
 **/MANIFESTINPUT** параметр указывает путь к входной файл, используемый для создания внедренного манифеста в исполняемый образ. Если у вас есть несколько манифест входные файлы, используйте параметр несколько раз — один раз для каждого входного файла. Чтобы создать внедренный манифест объединяются входных файлов манифеста. Этот параметр требует **/MANIFEST: внедрить** параметр.  
  
 Этот параметр невозможно задать непосредственно в [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Вместо этого используйте **дополнительные файлы манифеста** свойство проекта, чтобы указать дополнительные файлы манифеста для включения. Дополнительные сведения см. в разделе [ввода и вывода, инструмент манифеста, свойства конфигурации \<имя_проекта > страницы свойств-диалоговое окно](../../ide/input-and-output-manifest-tool.md).  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)