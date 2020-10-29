---
title: /DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)
description: Параметр/ДЕПЕНДЕНТЛОАДФЛАГ устанавливает зависимые по умолчанию флаги загрузки для библиотек DLL, загруженных этим модулем.
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 8d0f53ed13143ed7ff5c507df73937a86c07b5b8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924213"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)

::: moniker range="msvc-140"

Для использования параметра **/депендентлоадфлаг** требуется Visual Studio 2017 или более поздней версии.

::: moniker-end

::: moniker range=">=msvc-150"

Задает флаги загрузки по умолчанию, используемые, когда операционная система разрешает статически связанные импорты модуля.

## <a name="syntax"></a>Синтаксис

> **/Депендентлоадфлаг** [ __:__*load_flags* ]

### <a name="arguments"></a>Аргументы

*load_flags*<br/>
Необязательное целочисленное значение, указывающее флаги нагрузки, применяемые при разрешении статически связанных зависимостей импорта модуля. Значение по умолчанию — 0. Список поддерживаемых значений флагов см `LOAD_LIBRARY_SEARCH_*` . в записи в [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

## <a name="remarks"></a>Remarks

Когда операционная система разрешает статически связанные импорты модуля, он использует [Порядок поиска по умолчанию](/windows/win32/dlls/dynamic-link-library-search-order). Используйте параметр **/депендентлоадфлаг** , чтобы указать значение *load_flags* , которое изменяет путь поиска, используемый для разрешения этих импортов. В поддерживаемых операционных системах он изменяет порядок поиска статического разрешения импорта, аналогично тому, что [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) делает при использовании `LOAD_LIBRARY_SEARCH` параметров. Сведения о порядке поиска, заданном *load_flags* , см. в разделе [Порядок поиска с помощью флагов LOAD_LIBRARY_SEARCH](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

Этот флаг можно использовать для того, чтобы одна [Библиотека DLL не плантинг атаки](/windows/win32/dlls/dynamic-link-library-security) вектором. Например, рассмотрим приложение со статическим связыванием библиотеки DLL:

- Злоумышленник может растенить библиотеку DLL с тем же именем ранее в пути поиска для разрешения импорта, например в каталоге приложения. Защищенные каталоги сложнее, но не могут быть изменены злоумышленником.

- Если библиотека DLL отсутствует в каталогах Application,%Windows%\System32 и% Windows%, то разрешение импорта попадает в текущий каталог. Злоумышленник может растенить библиотеку DLL.

В обоих случаях при указании параметра Link `/DEPENDENTLOADFLAG:0x800` (значение флага `LOAD_LIBRARY_SEARCH_SYSTEM32` ) путь поиска модуля ограничен каталогом%Windows%\System32. Она обеспечивает некоторую защиту от атак плантинг на другие каталоги. Дополнительные сведения см. в статье [безопасность библиотеки динамической компоновки](/windows/win32/dlls/dynamic-link-library-security).

Чтобы просмотреть значение, заданное параметром **/депендентлоадфлаг** в любой библиотеке DLL, используйте команду [dumpbin](dumpbin-reference.md) с параметром [/лоадконфиг](loadconfig.md) .

Параметр **/депендентлоадфлаг** является новым в Visual Studio 2017. Он применяется только к приложениям, работающим в Windows 10 RS1 и более поздних версий. Этот параметр игнорируется другими операционными системами, на которых выполняется приложение.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика ДЕПЕНДЕНТЛОАДФЛАГ в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **Компоновщик** > **Командная строка** .

1. Введите параметр в поле **Дополнительные параметры** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также статью

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [Неявное связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Определение подходящего метода связывания](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Порядок поиска библиотеки динамической компоновки (DLL)](/windows/win32/Dlls/dynamic-link-library-search-order)
- [Безопасность библиотеки динамической компоновки](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end
