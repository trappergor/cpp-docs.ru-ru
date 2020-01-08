---
title: /DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)
description: Параметр/ДЕПЕНДЕНТЛОАДФЛАГ устанавливает флаги по умолчанию для библиотек DLL, загруженных с помощью LoadLibrary
ms.date: 12/22/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 3a403f22c88ccd3e25ba95c183656ad2ffafd05a
ms.sourcegitcommit: ef34a11cb04511221bf5c7b9f4f55ad91a7a603f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2019
ms.locfileid: "75330002"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)

Задает флаги загрузки по умолчанию, используемые, когда `LoadLibrary` используется для загрузки библиотек DLL.

## <a name="syntax"></a>Синтаксис

> **/Депендентлоадфлаг**[ __:__ *load_flags*]

### <a name="arguments"></a>Arguments

*load_flags*<br/>
Необязательное 16-разрядное целое число в стиле C в десятичном, восьмеричное с нулем в начале или в шестнадцатеричном виде с ведущим `0x`, которое указывает зависимые флаги нагрузки, применяемые ко всем вызовам [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) . По умолчанию используется значение 0.

## <a name="remarks"></a>Заметки

Этот вариант является новым в Visual Studio 2017. Он применяется только к приложениям, работающим в Windows 10 RS1 и более поздних версий. Этот параметр игнорируется другими операционными системами, на которых выполняется приложение.

В поддерживаемых операционных системах этот параметр влияет на изменение вызовов в `LoadLibrary("dependent.dll")` эквивалентом `LoadLibraryEx("dependent.dll", 0, load_flags)`. Вызовы к [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) не затрагиваются. Этот параметр не применяется рекурсивно к библиотекам DLL, загруженным приложением.

Этот флаг можно использовать, чтобы сделать [плантинг атаки DLL](/windows/win32/dlls/dynamic-link-library-security) более сложной. Например, если приложение использует `LoadLibrary` для загрузки зависимой библиотеки DLL, злоумышленник может подставлять библиотеку DLL с тем же именем в пути поиска, используемом `LoadLibrary`, например текущим каталогом, который может быть проверен перед системными каталогами, если защищенный режим поиска DLL отключен. Режим поиска в защищенных библиотеках DLL помещает текущий каталог пользователя в порядок поиска и включается по умолчанию в Windows XP с пакетом обновления 2 (SP2) и более поздних версиях. Дополнительные сведения см. в статье [Порядок поиска библиотек динамической компоновки](/windows/win32/Dlls/dynamic-link-library-search-order).

Если указать параметр ссылки `/DEPENDENTLOADFLAG:0xA00` (значение Объединенных флагов `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), то даже если на компьютере пользователя отключен режим поиска с помощью безопасного DLL-файла, путь поиска DLL будет ограничен каталогом приложения, за которым следует каталог%Windows%\System32. Параметр `/DEPENDENTLOADFLAG:0x800` является еще более ограничивающим, ограничивая Поиск в каталоге%Windows%\System32. Защищенные каталоги сложнее, но не могут быть изменены злоумышленником. Сведения о доступных флагах и их символьных и числовых значениях см. в описании параметра *dwFlags* в [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw). Сведения о порядке поиска, используемом при использовании различных зависимых флагов нагрузки, см. в разделе [Порядок поиска с использованием флагов LOAD_LIBRARY_SEARCH](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика ДЕПЕНДЕНТЛОАДФЛАГ в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **Компоновщик** > **Командная строка**.

1. Введите параметр в поле **Дополнительные параметры**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Порядок поиска библиотек динамической компоновки](/windows/win32/Dlls/dynamic-link-library-search-order)
