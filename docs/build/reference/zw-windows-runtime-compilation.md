---
title: -ZW (компиляция среды выполнения Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs:
- C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97a97158dda886a09fb6ccb00898a8c518d8e250
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602266"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (компиляция среды выполнения Windows)
Компилирует исходный код для поддержки расширения компонентов Visual C++ C + +/ CX для создания приложений универсальной платформы Windows (UWP).  
  
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
 При указании **/ZW** параметр, компилятор поддерживает следующие функции:  
  
-   Необходимые метаданные файлов, пространств имен, типов данных и функций, которые необходимы приложению для выполнения в среде выполнения Windows.  
  
-   Автоматический подсчет ссылок на объекты среды выполнения Windows и автоматическое удаление объекта, когда его счетчик ссылок становится равен нулю.  
  
 Так как Инкрементный компоновщик не поддерживает метаданные Windows, входящие в OBJ-файлов с помощью **/ZW** параметр, [/Gm (включение минимального перепостроения)](../../build/reference/gm-enable-minimal-rebuild.md) не совместим с **/ZW** .  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)