---
title: "-FUNCTIONPADMIN (создать образ с обновлениями) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (создание образа, допускающего горячее обновление)
Готовит образ к оперативному исправлению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `space` (необязательно)  
 Количество битов разреживания Добавление в начале каждой функции, 5, 6 или 16.  x86 изображения требуют пять байт заполнения, x64 изображения требуют 6 байт и образы, создаваемые для процессоров семейства Itanium требуют 16 байтов заполнения в начале каждой функции.  
  
 По умолчанию компилятор добавит требуемый объем изображения, основанный на типе машины образа.  
  
 Чтобы компоновщику создать образ с обновлениями, OBJ-файлы, должны компилироваться с [/hotpatch (создать образ с обновлениями)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 При компиляции и компоновки образа с одного вызова рабочей cl.exe, **/hotpatch** подразумевает **/functionpadmin**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)