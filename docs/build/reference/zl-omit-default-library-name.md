---
title: -Zl (опустить имя библиотеки по умолчанию) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
dev_langs:
- C++
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c14a3217334c2c43bac7fbcce8b0bfd60a609d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379722"
---
# <a name="zl-omit-default-library-name"></a>/Zl (Опущенное по умолчанию имя библиотеки)
Пропускает имя библиотеки времени выполнения C по умолчанию из OBJ-файле. По умолчанию компилятор помещает имя библиотеки в OBJ-файл, чтобы перенаправить компоновщик в правильную библиотеку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zl  
```  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о библиотеке по умолчанию см. в разделе [использование библиотеки времени выполнения](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 Можно использовать **/Zl** для компиляции OBJ-файлы, которые планируется включить в библиотеку. Несмотря на то, что опустить имя библиотеки сохраняет только небольшой объем пространства для одном obj-файле, всего пространства, освобождаемого важен в библиотеку, которая содержит много модулей объекта.  
  
 Этот параметр является дополнительным параметром. Если этот параметр удаляет определенные поддержка библиотеки времени выполнения C, могут потребоваться для вашего приложения, в результате чего ошибки во время компоновки, если ваше приложение зависит от этой поддержки. При использовании этого параметра необходимо указать необходимые компоненты иным способом.  
  
 Используйте [/NODEFAULTLIB (пропуск библиотек)](../../build/reference/nodefaultlib-ignore-libraries.md). Чтобы перенаправить компоновщик игнорировал библиотечные ссылки во все OBJ-файлы.  
  
 Дополнительные сведения см. в разделе [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
 При компиляции с параметром **/Zl**, `_VC_NODEFAULTLIB` определен.  Пример:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **опустить имена библиотек по умолчанию** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)