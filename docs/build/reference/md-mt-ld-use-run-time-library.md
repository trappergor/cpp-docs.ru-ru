---
title: "-MD, -MT, -LD (использование библиотеки времени выполнения) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
dev_langs: C++
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b54a6aac55554cd7bd4698762779e540c4bc4c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (использование библиотеки времени выполнения)
Указывает, является ли многопоточный модуль библиотекой DLL, и задает версию библиотеки времени выполнения для отладки или выпуска.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## <a name="remarks"></a>Примечания  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**/MD**|Предписывает приложению использование специальной многопоточной и зависящей от DLL версии библиотеки времени выполнения. Определяет параметры `_MT` и `_DLL` и предписывает компилятору размещение имени библиотеки MSVCRT.lib в OBJ-файле.<br /><br /> Приложения, компилируемые с этим параметром, статически компонуются с библиотекой MSVCRT.lib. Эта библиотека содержит слой кода, позволяющий компоновщику разрешить внешние ссылки. Фактические работавшего кода содержится в MSVCR*Номер_версии*. Библиотеки DLL, которая должна быть доступна во время выполнения приложений, связанных с библиотекой MSVCRT.lib.|  
|**/MDd**|Определяет параметры `_DEBUG`, `_MT` и `_DLL` и предписывает приложению использование отладочной многопоточной и зависящей от DLL версии библиотеки времени выполнения. Также предписывает компилятору размещение имени библиотеки MSVCRTD.lib в .obj-файле.|  
|**/MT**|Предписывает приложению использовать многопоточную статическую версию библиотеки времени выполнения. Создает определение `_MT` и указывает компилятору на необходимость размещения имени библиотеки LIBCMT.lib в файле OBJ, чтобы компоновщик использовал библиотеку LIBCMT.lib для разрешения внешних символов.|  
|**/MTd**|Создает определения `_DEBUG` и `_MT`. Этот параметр также предписывает компилятору размещение имени библиотеки LIBCMTD.lib в .obj-файле, чтобы компоновщик использовал LIBCMTD.lib для разрешения внешних символов.|  
|**/LD**|Создает библиотеку DLL.<br /><br /> Передает **/DLL** параметр в компоновщик. Компоновщик будет искать функцию `DllMain`; тем не менее, она не является обязательной. Если функция `DllMain` отсутствует, компоновщик вставляет функцию `DllMain`, возвращающую значение TRUE.<br /><br /> Компонует код запуска библиотеки DLL.<br /><br /> Создает библиотеку импорта (LIB), если файл экспорта (EXP) не указан в командной строке. Библиотека импорта связывается с приложениями, которые вызывают библиотеку DLL.<br /><br /> Интерпретирует [/Fe (именование EXE-файла)](../../build/reference/fe-name-exe-file.md) как именование библиотеки DLL, а не файл .exe. По умолчанию становится имя программы *базовым именем*DLL-файл, а не *базовым именем*.exe.<br /><br /> Подразумевает **/MT** Если явно не указан **/MD**.|  
|**/ LDd**|Создает отладочную библиотеку DLL. Создает определения `_MT` и `_DEBUG`.|  
  
 Дополнительные сведения о библиотеках времени выполнения C и какие библиотеки будут использоваться при компиляции с параметром [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md), в разделе [возможности библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
 Все модули, передаваемые компоновщику при конкретном вызове, должны компилироваться с тем же параметром компилятора библиотеки времени выполнения (**/MD**, **/MT**, **/LD**).  
  
 Дополнительные сведения об использовании отладочных версий библиотек времени выполнения см. в разделе [Справочник по библиотеке времени выполнения C](../../c-runtime-library/c-run-time-library-reference.md).  
  
 В статье базы знаний Q140584 также описывается порядок выбора подходящей библиотеки времени выполнения C.  
  
 Дополнительные сведения о библиотеках DLL см. в разделе [библиотеки DLL в Visual C++](../../build/dlls-in-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **C/C++** папки.  
  
3.  Выберите **создания кода** страницу свойств.  
  
4.  Изменить **библиотеки времени выполнения** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)