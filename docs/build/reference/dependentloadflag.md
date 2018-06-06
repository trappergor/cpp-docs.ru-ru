---
title: / DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)
description: Параметр /DEPENDENTLOADFLAG задает флаги по умолчанию для библиотеки DLL, загруженные с помощью LoadLibrary
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dependentloadflag
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a171f3c2edbbbf614a986ff78dd2405e734a1d1
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753717"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)

Задает флаги загрузки по умолчанию, используемые при `LoadLibrary` используется для загрузки библиотеки DLL.

## <a name="syntax"></a>Синтаксис

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>Аргументы

|||
|-|-|
*loadflags*|Необязательное значение «C» стиле 16-разрядное целое число в десятичное число, с нулем в начале восьмеричные и шестнадцатеричные с символа `0x`, указывающее флаги зависимой загрузки применить ко всем [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) вызовов. Значение по умолчанию — 0.

## <a name="remarks"></a>Примечания

Этот параметр, новые возможности Visual Studio 2017 г. и применяется только к приложениям, под управлением Windows 10 RS1 и более поздних версиях. Этот параметр учитывается в других операционных системах, запустите приложение.

В поддерживаемых операционных системах, этот параметр может иметь эффект от изменения вызовы `LoadLibrary("dependent.dll")` эквивалент следующего `LoadLibraryEx("dependent.dll", 0, loadflags)`. Вызовы [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) не затрагиваются. Этот параметр не применяется рекурсивно для загруженных приложением DLL.

Этот флаг используется для предотвращения подмены атак DLL. Например, если приложение использует `LoadLibrary` загрузить зависимую библиотеку DLL, злоумышленник, можно запустить библиотеку DLL с тем же именем в путь поиска, используемый `LoadLibrary`, например текущий каталог, который может проверяться перед системные каталоги Если безопасный режим поиска библиотеки DLL отключено. Безопасный режим поиска библиотеки DLL помещает каталога текущего пользователя позже в порядке поиска и включен по умолчанию в Windows XP SP2 и более поздних версиях. Дополнительные сведения см. в разделе [порядок поиска библиотек динамической компоновки](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

При указании параметра ссылку `/DEPENDENTLOADFLAG:0xA00` (значение флагов объединенный `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), то ограничено даже при отключении безопасный режим поиска библиотеки DLL на компьютере пользователя, защищенных каталогов, которые сложнее злоумышленнику пути поиска DLL изменение. Сведения о доступных флагов и их символьных и числовых значений см. в разделе *dwFlags* описание параметра в [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика DEPENDENTLOADFLAG в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](setting-linker-options.md)
- [Параметры компоновщика](linker-options.md)
- [Неявное связывание с библиотекой DLL](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Определение подходящего метода связывания](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [Порядок поиска библиотеки динамической компоновки](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)
