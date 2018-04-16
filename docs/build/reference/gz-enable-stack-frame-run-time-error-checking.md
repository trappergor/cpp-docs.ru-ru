---
title: -GZ (включить стека ошибки во время выполнения проверку фрейма) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /gz
dev_langs:
- C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 621878aacaf2a1b36ed0014451ada504d8a24556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Позволяет проверку фрейма стека ошибки во время выполнения)
Выполняет те же операции, как [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) параметр. Не рекомендуется.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GZ  
```  
  
## <a name="remarks"></a>Примечания  
 **/GZ** предназначен только для использования в неоптимизированном ([/Od (Выключение (отладчика))](../../build/reference/od-disable-debug.md)) сборки.  
  
 **/GZ** является устаревшим, так как Visual Studio 2005; используйте [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) вместо него. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)