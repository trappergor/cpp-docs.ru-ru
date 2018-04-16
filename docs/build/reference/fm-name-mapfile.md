---
title: -Fm-(имя файла сопоставления) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a5111291ea92b8650896faf3117f0056510e5ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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