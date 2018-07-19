---
title: -Fm-(имя файла сопоставления) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a499b943fcd3213aa76876c65c3aac2dd79060
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374288"
---
# <a name="fm-name-mapfile"></a>Параметр /Fm (имя файла сопоставления)
Указывает компоновщику создать файл сопоставления, содержащий список сегментов в том порядке, в котором они появляются в соответствующий файл .exe или DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию получает имя базового C или C++ исходный файл с файл сопоставления. Расширение КАРТЫ.  
  
 Указание **/Fm** действует так же, как если бы [/Map (Создание файла сопоставления)](../../build/reference/map-generate-mapfile.md) компоновщика.  
  
 При указании [/c (компиляция без связывания)](../../build/reference/c-compile-without-linking.md) запрещающий связывание, **/Fm** не делает ничего.  
  
 Глобальные символы в файл сопоставления обычно имеет один или несколько со знака подчеркивания, поскольку компилятор добавляет подчеркивания в именах переменных. Многие из глобальных символов, присутствующих в файле сопоставления используются компилятором, и стандартные библиотеки.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)