---
title: / DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)
description: Параметр /DEPENDENTLOADFLAG задает флаги по умолчанию для библиотек DLL, загруженные с помощью LoadLibrary
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 94998e06f23a7e70524221d3cb75166b5d3f2c44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272091"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (зависимой загрузки флаги, заданные по умолчанию)

Задает флаги нагрузки по умолчанию используется, когда `LoadLibrary` используется для загрузки библиотеки DLL.

## <a name="syntax"></a>Синтаксис

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>Аргументы

*loadflags*<br/>
Необязательное значение 16-разрядное целое число «C "стиле в десятеричной, восьмеричной с нулем или шестнадцатеричное, начинающиеся с символа `0x`, который указывает флаги зависимой загрузки, чтобы применить ко всем [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) вызовов. Значение по умолчанию — 0.

## <a name="remarks"></a>Примечания

Этот параметр впервые появился в Visual Studio 2017 и применяется только к приложениям, под управлением Windows 10 RS1 и более поздних версий. Этот параметр игнорируется другими операционными системами, запустите приложение.

В поддерживаемых операционных системах, этот параметр имеет эффект от изменения вызовов `LoadLibrary("dependent.dll")` в эквивалент `LoadLibraryEx("dependent.dll", 0, loadflags)`. Вызовы [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa) не затрагиваются. Этот параметр не применяется рекурсивно для загруженных приложением библиотек DLL.

Этот флаг можно использовать для предотвращения подмены атак библиотеки DLL. Например, если приложение использует `LoadLibrary` загрузить зависимую библиотеку DLL, злоумышленник, можно запустить библиотеку DLL с тем же именем в путь поиска, используемый `LoadLibrary`, например текущий каталог, который может проверяться перед системные каталоги Если безопасный режим поиска библиотеки DLL отключена. Безопасный режим поиска DLL помещает текущий каталог пользователя позже в порядок поиска и включен по умолчанию в Windows XP SP2 и более поздних версий. Дополнительные сведения см. в разделе [порядок поиска библиотеки динамической компоновки](/windows/desktop/Dlls/dynamic-link-library-search-order).

При использовании параметра ссылку `/DEPENDENTLOADFLAG:0xA00` (значение флагов объединенный `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), то даже если безопасный режим поиска DLL отключена на компьютере пользователя, путь поиска DLL будут ограничены защищенных каталогов, которые сложнее злоумышленнику изменение. Сведения о флагах и их символьные и числовые значения, см. в разделе *dwFlags* описание параметра в [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика DEPENDENTLOADFLAG в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)
- [Порядок поиска библиотеки динамической компоновки](/windows/desktop/Dlls/dynamic-link-library-search-order)
