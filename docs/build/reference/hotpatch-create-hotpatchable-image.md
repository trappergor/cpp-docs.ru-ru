---
title: -hotpatch (создать образ с обновлениями) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb0f27c8da03104ee3633d9ea1a5f1232407931e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Создать образ с обновлениями)
Готовит образ к оперативному исправлению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/hotpatch  
```  
  
## <a name="remarks"></a>Примечания  
 Когда **/hotpatch** используется во время компиляции, компилятор гарантирует, что первой инструкции каждой функции по крайней мере два байта, которая необходима для выполнения горячего обновления.  
  
 Чтобы завершить подготовку для создания образа с обновлениями, после использования **/hotpatch** для компиляции, необходимо использовать [/FUNCTIONPADMIN (создать образ с обновлениями)](../../build/reference/functionpadmin-create-hotpatchable-image.md) для связывания. После компиляции и связать образ с помощью одного вызова cl.exe, **/hotpatch** подразумевает **/functionpadmin**.  
  
 Так как инструкции всегда два байта или больше для архитектуры ARM, а потому, что x64 компиляции всегда рассматривается как если бы **/hotpatch** был указан, нет необходимости указывать **/hotpatch** при Компилировать для этих целевых объектов; Однако по-прежнему необходимо связать с помощью **/functionpadmin** создание образов с обновлениями для них. **/Hotpatch** компиляции x86 влияет только параметр компилятора.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Добавить параметр компилятора для **Дополнительные параметры** поле.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="guidance"></a>Руководство  
 Дополнительные сведения об управлении обновлениями см. в разделе «Руководство по безопасности для обновления управления» в [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)