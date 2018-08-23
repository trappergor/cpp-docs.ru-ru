---
title: / DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)
description: Параметр /DEPENDENTLOADFLAG задает флаги по умолчанию для библиотек DLL, загруженные с помощью LoadLibrary
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
ms.openlocfilehash: 94f7667d7da8d8e9cd7ef38cb01d0f03b0da82e3
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572895"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)

Задает флаги нагрузки по умолчанию используется, когда `LoadLibrary` используется для загрузки библиотеки DLL.

## <a name="syntax"></a>Синтаксис

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>Аргументы

|||
|-|-|
*loadflags*|Необязательное значение 16-разрядное целое число «C "стиле в десятеричной, восьмеричной с нулем или шестнадцатеричное, начинающиеся с символа `0x`, который указывает флаги зависимой загрузки, чтобы применить ко всем [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) вызовов. Значение по умолчанию — 0.

## <a name="remarks"></a>Примечания

Этот параметр впервые появился в Visual Studio 2017 и применяется только к приложениям, под управлением Windows 10 RS1 и более поздних версий. Этот параметр игнорируется другими операционными системами, запустите приложение.

В поддерживаемых операционных системах, этот параметр имеет эффект от изменения вызовов `LoadLibrary("dependent.dll")` в эквивалент `LoadLibraryEx("dependent.dll", 0, loadflags)`. Вызовы [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) не затрагиваются. Этот параметр не применяется рекурсивно для загруженных приложением библиотек DLL.

Этот флаг можно использовать для предотвращения подмены атак библиотеки DLL. Например, если приложение использует `LoadLibrary` загрузить зависимую библиотеку DLL, злоумышленник, можно запустить библиотеку DLL с тем же именем в путь поиска, используемый `LoadLibrary`, например текущий каталог, который может проверяться перед системные каталоги Если безопасный режим поиска библиотеки DLL отключена. Безопасный режим поиска DLL помещает текущий каталог пользователя позже в порядок поиска и включен по умолчанию в Windows XP SP2 и более поздних версий. Дополнительные сведения см. в разделе [порядок поиска библиотеки динамической компоновки](/windows/desktop/Dlls/dynamic-link-library-search-order).

При использовании параметра ссылку `/DEPENDENTLOADFLAG:0xA00` (значение флагов объединенный `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), то даже если безопасный режим поиска DLL отключена на компьютере пользователя, путь поиска DLL будут ограничены защищенных каталогов, которые сложнее злоумышленнику изменение. Сведения о флагах и их символьные и числовые значения, см. в разделе *dwFlags* описание параметра в [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика DEPENDENTLOADFLAG в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

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
- [Порядок поиска библиотеки динамической компоновки](/windows/desktop/Dlls/dynamic-link-library-search-order)
