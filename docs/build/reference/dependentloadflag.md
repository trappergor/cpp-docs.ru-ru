---
title: /DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)
description: Параметр/ДЕПЕНДЕНТЛОАДФЛАГ устанавливает флаги по умолчанию для библиотек DLL, загруженных с помощью LoadLibrary
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 072fa1103d049c7d5c395ae88d268f3b47e20b4f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492955"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (установка флагов зависимой загрузки по умолчанию)

Задает флаги загрузки по умолчанию `LoadLibrary` , используемые при загрузке библиотек DLL.

## <a name="syntax"></a>Синтаксис

> **/Депендентлоадфлаг** [ **:** _лоадфлагс_]

### <a name="arguments"></a>Аргументы

*лоадфлагс*<br/>
Необязательное 16-разрядное целое число в стиле C в десятичном, восьмеричное с нулем в начале или в шестнадцатеричном формате с начальным `0x`значением, которое указывает зависимые флаги нагрузки, применяемые ко всем вызовам [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) . Значение по умолчанию — 0.

## <a name="remarks"></a>Примечания

Этот вариант является новым в Visual Studio 2017 и применяется только к приложениям, работающим в Windows 10 RS1 и более поздних версий. Этот параметр игнорируется другими операционными системами, на которых выполняется приложение.

В поддерживаемых операционных системах этот параметр влияет на изменение вызовов `LoadLibrary("dependent.dll")` к `LoadLibraryEx("dependent.dll", 0, loadflags)`эквиваленту. Вызовы к [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) не затрагиваются. Этот параметр не применяется рекурсивно к библиотекам DLL, загруженным приложением.

Этот флаг можно использовать для предотвращения атак плантинг DLL. Например, если приложение использует `LoadLibrary` для загрузки зависимой библиотеки DLL, злоумышленник может растенить библиотеку DLL с тем же именем в пути поиска `LoadLibrary`, используемом, например, текущим каталогом, который может быть проверен перед системными каталогами, если защищенный режим поиска DLL доступ. Режим поиска в защищенных библиотеках DLL помещает текущий каталог пользователя в порядок поиска и включается по умолчанию в Windows XP с пакетом обновления 2 (SP2) и более поздних версиях. Дополнительные сведения см. в статье [Порядок поиска библиотек динамической компоновки](/windows/win32/Dlls/dynamic-link-library-search-order).

Если указать параметр `/DEPENDENTLOADFLAG:0xA00` Link (значение Объединенных флагов `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), то даже если на компьютере пользователя отключен режим поиска с помощью безопасного DLL-файла, путь поиска DLL будет ограничен защищенными каталогами, которые более трудны для злоумышленника смен. Сведения о доступных флагах и их символьных и числовых значениях см. в описании параметра *dwFlags* в [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Установка параметра компоновщика ДЕПЕНДЕНТЛОАДФЛАГ в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойства**командной строки** **компоновщика** >  **свойств** > конфигурации.

1. Введите параметр в поле **Дополнительные параметры**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Связывание исполняемого файла с библиотекой DLL](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Порядок поиска библиотек динамической компоновки](/windows/win32/Dlls/dynamic-link-library-search-order)
