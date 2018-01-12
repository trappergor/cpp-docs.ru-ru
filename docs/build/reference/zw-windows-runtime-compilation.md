---
title: "-ZW (компиляция среды выполнения Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs: C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75f46c2eaaa42f473e02bc553dd06b86cd5bbc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (компиляция среды выполнения Windows)
Компилирует исходный код для поддержки [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) при создании приложений [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  
  
 При использовании **/ZW** для компиляции, всегда указывайте **/EHsc** также.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>Аргументы  
 nostdlib  
 Указывает на то, что Platform.winmd, Windows.Foundation.winmd и другие файлы метаданных Windows по умолчанию (WINMD) не включаются в компиляцию автоматически. Вместо этого необходимо использовать [/FU (имя принудительно #using файла)](../../build/reference/fu-name-forced-hash-using-file.md) параметр компилятора, чтобы явным образом указать файлы метаданных Windows.  
  
## <a name="remarks"></a>Примечания  
 При указании **/zw** параметр, компилятор поддерживает следующие возможности:  
  
-   Файлы метаданных, пространства имен, типов данных и функций, которые приложение требуется для выполнения в среде выполнения Windows.  
  
-   Автоматический подсчет ссылок на объекты среды выполнения Windows и автоматическое удаление объекта, когда число ссылок становится равен нулю.  
  
 Инкрементный компоновщик поддерживает метаданные Windows, включенные в OBJ-файлов с помощью **/ZW** параметр [/Gm (включение минимального перепостроения)](../../build/reference/gm-enable-minimal-rebuild.md) несовместим с   **/zw** .  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)