---
title: /ENTRY (символ точки входа)
ms.date: 11/04/2016
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
ms.openlocfilehash: 5ebc18d6d895928b1deec392cbb0bd91f48a96ed
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425709"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (символ точки входа)

```
/ENTRY:function
```

## <a name="arguments"></a>Аргументы

*function*<br/>
Функция, которая определяет пользовательские начальный адрес для библиотеки DLL или файла .exe.

## <a name="remarks"></a>Примечания

Параметр/Entry задает функцию точки входа в качестве начального адреса для библиотеки DLL или файла .exe.

Функция должна быть определена для использования `__stdcall` соглашение о вызовах. Параметры и возвращаемые значения зависят от ли программы консольного приложения, приложения windows или библиотеку DLL. Рекомендуется разрешить компоновщику установить точку входа, чтобы правильно инициализации библиотеки времени выполнения C и C++ конструкторы для статических объектов выполняются.

По умолчанию начальный адрес — имя функции из библиотеки времени выполнения C. Компоновщик выбирает ее в соответствии с атрибутами программы, как показано в следующей таблице.

|Имя функции|Значение по умолчанию для|
|-------------------|-----------------|
|**mainCRTStartup** (или **wmainCRTStartup**)|Приложения, использующего/SUBSYSTEM: Console; вызовы `main` (или `wmain`)|
|**Случае** (или **wWinMainCRTStartup**)|Приложения, использующего параметр/SUBSYSTEM:**WINDOWS**; вызовы `WinMain` (или `wWinMain`), который должен быть определен для использования `__stdcall`|
|**_DllMainCRTStartup**|БИБЛИОТЕКИ DLL; вызовы `DllMain` если он существует, который должен быть определен для использования `__stdcall`|

Если [/DLL](../../build/reference/dll-build-a-dll.md) или [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметр не указан, компоновщик выбирает подсистему и точку входа в зависимости от того `main` или `WinMain` определен.

Функции `main`, `WinMain`, и `DllMain` приведены три формы точки входа, определяемые пользователем.

При создании управляемого образа, функцию, указанную для/Entry должны иметь подпись (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Сведения о том, как определять свои собственные `DllMain` точки входа, см. в разделе [библиотеки DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **точки входа** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
