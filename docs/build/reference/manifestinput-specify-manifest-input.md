---
title: "-MANIFESTINPUT (задание входных данных манифеста) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a32eb8c65e14684b818341121714ce0359f6521a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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