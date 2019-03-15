---
title: /STUB (имя файла-заглушки MS-DOS)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 7150d4ff8f35b00d96caa21fd5ea3754fec76030
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822409"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (имя файла-заглушки MS-DOS)

```
/STUB:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Приложение MS-DOS.

## <a name="remarks"></a>Примечания

Параметр/STUB присоединяет программу-заглушку MS-DOS к программе Win32.

Программу-заглушку вызывается в том случае, если этот файл исполняется в MS-DOS. Как правило, выводится соответствующее сообщение; Однако любое допустимое приложение MS-DOS может быть программу-заглушку.

Укажите *filename* для программу-заглушку после двоеточия (:) в командной строке. Компоновщик проверяет *filename* и выдает сообщение об ошибке, если файл не является исполняемым файлом. Программа должна быть файл .exe; .com файл является недопустимым для программу-заглушку.

Если этот параметр не используется, компоновщик присоединяет программу-заглушку по умолчанию, выдает следующее сообщение:

```
This program cannot be run in MS-DOS mode.
```

При построении драйвер виртуального устройства, *filename* позволяет пользователю указать имя файла, который содержит структуру IMAGE_DOS_HEADER (определенную в файле WINNT. H) для использования в VXD вместо заголовка по умолчанию.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
