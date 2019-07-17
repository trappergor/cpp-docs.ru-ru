---
title: Инструменты и функции C++ в выпусках Visual Studio
ms.date: 05/21/2019
helpviewer_keywords:
- tools and platforms [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: a7514e5cc52b24740b82cc067e77955c4784c9f0
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400630"
---
# <a name="c-tools-and-features-in-visual-studio-editions"></a>Инструменты и функции C++ в выпусках Visual Studio


::: moniker range=">=vs-2019"


Следующие функции C++ доступны в Visual Studio 2019. Если не указано иное, все функции доступны во всех выпусках: Visual Studio Community, Visual Studio Professional и Visual Studio Enterprise. Некоторые функции требуют конкретных рабочих нагрузок или дополнительных компонентов, которые можно установить с помощью Visual Studio Installer.

## <a name="platforms"></a>Платформы

- Windows Desktop
- Универсальная платформа Windows (планшеты, ПК, Xbox, IoT и HoloLens)
- Linux
- Android
- iOS

## <a name="compilers"></a>Компиляторы

- 32-разрядный компилятор MSVC для x86, x 64, ARM и ARM64
- 64-разрядный компилятор MSVC для x86, x 64, ARM и ARM64
- Кросскомпилятор GCC для ARM
- Clang/LLVM
  - В Windows Clang/LLVM 7.0 для x86 или x64 (поддержка только CMake). Другие версии Clang могут работать, но официально не поддерживаются.
  - Любая установка Clang/LLVM поддерживается дистрибутивом Linux.
 
## <a name="c-workloads"></a>Рабочие нагрузки C++

Visual Studio включает в себя следующие рабочие нагрузки для разработок на C++. Вы можете установить любые или все из них, а также другие рабочие нагрузки, например разработка классических приложений .NET, разработка на Python, разработка для Azure, разработка расширений Visual Studio и другие.

### <a name="desktop-development-with-c"></a>Разработка классических приложений на C++

Включено:
- Основные возможности C++ для классических приложений

Необязательные компоненты:
- MSVC версии 142 — средства сборки C++ для VS 2019 для 64- или 32-разрядных систем (версия 14.21)
- Пакет SDK для Windows 10 (10.0.17763.0)
- JIT-отладчик
- Средства профилирования C++
- Средства CMake C++ для Windows
- ATL C++ для средств сборки версии 142 (x86 и x64)
- Адаптер теста для Boost.Test
- Адаптер тестов для Google Test
- Live Share
- IntelliCode
- IntelliTrace (только в выпуске Enterprise)
- MFC C++ для средств сборки версии 142 (x86 и x64)
- Поддержка C++/CLI для средств сборки версии 142 (14.21)
- Модули C++ для средств сборки версии 142 (x64 или x86 — экспериментальная)
- Компилятор Clang для Windows
- IncrediBuild — ускорение сборки
- Пакет SDK для Windows 10 (10.0.17134.0)
- Пакет SDK для Windows 10 (10.0.16299.0)
- MSVC версии 141 — средства сборки C++ для VS 2017 для 64- или 32-разрядных систем (версия 14.16)
- MSVC версии 140 — средства сборки C++ VS 2015 (версия 14.00)

### <a name="linux-development-with-c"></a>Разработка приложений для Linux на C++

Включено:
- Основные компоненты C++
- Универсальная среда выполнения C для Windows
- Разработка на C++ для Linux

Необязательные компоненты:
- Средства CMake C++ для Linux
- Средства разработки для встроенных платформ и Интернета вещей

### <a name="universal-windows-platform-development"></a>Разработка с помощью универсальной платформы Windows

Включено:
- Blend для Visual Studio
- .NET Native и .NET Standard
- Диспетчер пакетов NuGet
- Средства универсальной платформы Windows
- Пакет SDK для Windows 10 (10.0.17763.0)

Необязательные компоненты:
- IntelliCode
- IntelliTrace (только в выпуске Enterprise)
- Подключение USB-устройств
- Средства универсальной платформы Windows на C++ (версия 142)
- Средства универсальной платформы Windows для C++ (v141)
- Отладчик графики и профилировщик GPU для DirectX
- Пакет SDK для Windows 10 (10.0.18362.0)
- Пакет SDK для Windows 10 (10.0.17134.0)
- Пакет SDK для Windows 10 (10.0.16299.0)
- Инструменты архитектуры и анализа

### <a name="c-game-development"></a>Разработка игр на C++

Включено:
- Основные компоненты C++
- Универсальная среда выполнения C для Windows
- Обновление для распространяемого компонента C++ 2019
- MSVC версии 142 — средства сборки C++ для VS 2019 для 64- или 32-разрядных систем (версия 14.21)

Необязательные компоненты:
- Средства профилирования C++
- Пакет SDK для Windows 10 (10.0.17763.0)
- IntelliCode
- IntelliTrace (только в выпуске Enterprise)
- Пакет SDK для Windows 10 (10.0.17134.0)
- Пакет SDK для Windows 10 (10.0.16299.0)
- IncrediBuild — ускорение сборки
- Cocos
- Установщик Unreal Engine
- Поддержка IDE Android для Unreal Engine

### <a name="mobile-development-with-c"></a>Разработка мобильных приложений на C++

Включено:
- Основные компоненты C++
- Установка пакета SDK для Android (уровень API 25) (локальная установка для разработки мобильных приложений на C++)

Необязательные компоненты:
- NDK для Android (R16B)
- Apache Ant (1.9.3)
- Средства разработки на C++ для Android
- IntelliCode
- Google Android Emulator (уровень API 25), локальная установка
- Intel Hardware Accelerated Execution Manager (HAXM), локальная установка
- NDK для Android (R16B) (32-разрядный)
- Средства разработки C++ для iOS
- IncrediBuild — ускорение сборки


## <a name="individual-components"></a>Отдельные компоненты

Эти компоненты можно установить независимо друг от друга из любой рабочей нагрузки.

- Диагностика JavaScript
- Live Share
- Среда выполнения универсальной платформы Windows C++ для средств сборки версии 142
- Компонент для публикации ClickOnce
- Проекты Microsoft Visual Studio Installer

## <a name="libraries-and-headers"></a>Библиотеки и заголовки

- Заголовки и библиотеки Windows
- Универсальная среда выполнения C для Windows (CRT)
- Стандартная библиотека C++
- ATL
- MFC
- Библиотека классов .NET Framework
- Библиотека поддержки C++ для .NET
- OpenMP 2.0
- Более 900 библиотек с открытым кодом через каталог vcpkg

## <a name="build-and-project-systems"></a>Системы сборки и проектов

- CMake
- Любая система сборки через параметр "Открыть папку"
- Построение с помощью командной строки (msbuild.exe)
- Собственное многоплатформенное нацеливание
- Управляемое многоплатформенное нацеливание
- Параллельное построение
- Настройки сборки
- Расширяемость страниц свойств

## <a name="project-templates"></a>Шаблоны проектов

Указанные ниже шаблоны проектов доступны в зависимости от того, какие рабочие нагрузки установлены.

Рабочий стол Windows:
- Пустой проект
- Консольное приложение
- Мастер классических приложений Windows
- Классическое приложение Windows
- Проект общих элементов
- Приложение MFC
- Библиотека динамической компоновки
- Пустой проект CLR
- Консольное приложение CLR
- Статическая библиотека
- Проект CMake
- Проект ATL
- Библиотека динамической компоновки MFC
- Библиотека классов CLR
- Проект Makefile (Windows)
- MFC ActiveXControl
- Проект модульного теста в машинном коде
- Google Test

Универсальная платформа Windows (C++/CX):
- Пустое приложение
- Приложение DirectX 11 и XAML
- Приложение DirectX 11
- Приложение DirectX 12 
- Приложение модульных тестов 
- DLL 
- Компонент среды выполнения Windows 
- Статическая библиотека 
- Проект упаковки приложений Windows

Linux:
- Консольное приложение (Linux)
- Пустой проект (Linux)
- Raspberry Pi Blink
- Проект Makefile (Linux)

## <a name="tools"></a>Инструменты

- Инкрементный компоновщик (Link.exe)
- Служебная программа Microsoft Makefile (Nmake.exe)
- Генератор библиотек (Lib.exe)
- Компилятор ресурсов Windows (Rc.exe)
- Конвертер ресурсов Windows в объекты (CvtRes.exe)
- Служебная программа Browse Information Maintenance (BscMake.exe)
- C++ Name Undecorator (Undname.exe)
- COFF/PE Dumper (Dumpbin.exe)
- COFF/PE Editor (Editbin.exe)
- MASM (Ml.exe)
- Spy++
- ErrLook
- AtlTrace
- Правила вывода
- Оптимизация с использованием профиля

## <a name="debugging-features"></a>Средства отладки

- Отладка машинного кода
- natvis (визуализация собственного типа)
- Отладка графики
- Отладка управляемого кода
- Использование GPU
- Использование памяти
- Remote Debugging
- Отладка SQL
- Статический анализ кода

## <a name="designers-and-editors"></a>Редакторы и конструкторы

- Конструктор XAML
- Конструктор и редактор стилей CSS
- Конструктор и редактор HTML
- XML-редактор
- Редактор исходного кода
- Возможности повышения производительности: рефакторинг, подсистема IntelliSense EDG, форматирование кода C++
- Конструктор Windows Forms
- Конструктор данных
- Собственный редактор ресурсов (RC-файлы)
- редакторы ресурсов
- Редактор моделей
- Конструктор шейдеров
- Динамическая проверка зависимостей (только выпуск Enterprise)
- Диаграммы архитектурного уровня (только выпуск Enterprise)
- Проверка архитектуры (только выпуск Enterprise)
- Клонирование кода (только выпуск Enterprise)

## <a name="data-features"></a>Средства работы с данными

- Конструктор данных
- Объекты данных
- Веб-службы
- обозревателя серверов

## <a name="automation-and-extensibility"></a>Автоматизация и расширяемость

- Объектные модели расширения среды
- Модель кода
- модель проекта
- Модель редактора ресурсов
- Модель мастера
- Объектная модель отладчика

## <a name="application-lifecycle-management-tools"></a>Средства управления жизненным циклом приложения

- Модульное тестирование (Microsoft Native C++, Boost.Test, Google Test, CTest)
- Карта кода и диаграммы зависимостей (Professional и Enterprise)
- Покрытие кода (только Enterprise)
- Ручное тестирование (только Enterprise)
- Произвольное тестирование (только Enterprise)
- Управление тестовыми случаями (только Enterprise)
- Интеграция отладчика карты кода (только Enterprise)
- Live Unit Testing (только Enterprise)
- IntelliTrace (только в выпуске Enterprise)
- IntelliTest (только Enterprise)
- Microsoft Fakes (изоляция модульных тестов) (только Enterprise)
- Покрытие кода (только Enterprise)

## <a name="see-also"></a>См. также

[Установка Visual Studio](/visualstudio/install/install-visual-studio)<br/>
[Новые возможности Visual Studio](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Типы проектов C++ в Visual Studio](../build/reference/visual-cpp-project-types.md)

::: moniker-end

::: moniker range="<=vs-2017"

В следующей таблице перечислены компоненты Visual C++, доступные в Visual Studio 2017. Крестик в ячейке указывает, что компонент доступен. Пустая ячейка означает, что компонент недоступен. Примечания в скобках означают, что компонент доступен с ограничениями.

## <a name="platforms"></a>Платформы

||||||
|-|-|-|-|-|
|Platform|Visual Studio Express для Windows 10|Visual Studio Express для Windows Desktop|Visual Studio Community и Professional|Visual Studio Enterprise|
|Windows Desktop||X|X|X|
|Универсальная платформа Windows (телефоны, планшеты, ПК, Xbox, IoT и HoloLens)|X||X|X|
|Linux|X|X|
|Microsoft Store 8.1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Компиляторы

|Компилятор|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32-разрядный компилятор x86 MSVC|X|X|X|X|
|Кросс-компилятор X86_arm|X||X|X|
|64-разрядный компилятор x64 MSVC|||X|X|
|Кросс-компилятор X86_ x64|X|X|X|X|

## <a name="libraries-and-headers"></a>Библиотеки и заголовки

|Библиотека или заголовок|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Заголовки и библиотеки Windows; библиотека CRT|(X)|X|X|X|
|Стандартная библиотека C++|X|X|X|X|
|ATL|||X|X|
|MFC|||X|X|
|Библиотека классов .NET Framework||X|X|X|
|Библиотека поддержки C++ для .NET||X|X|X|
|OpenMP 2.0|X|X|X|X|

## <a name="project-templates"></a>Шаблоны проектов

|Шаблон|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Шаблоны XAML для UWP, Windows 8.1, Windows Phone 8.0|X||X|X|
|Приложение Direct3D|X||X|X|
|Библиотека DLL (универсальные приложения для Windows)|X||X|X|
|Статическая библиотека (универсальные приложения для Windows)|X||X|X|
|Компонент среды выполнения Windows|X||X|X|
|Приложение модульного тестирования (универсальное приложение Windows)|X||X|X|
|Проект ATL|||X|X|
|Библиотека классов (CLR)||X|X|X|
|Консольное приложение CLR||X|X|X|
|Пустой проект CLR||X|X|X|
|Специальный мастер|||X|X|
|Пустой проект||X|X|X|
|Проект, использующий файл makefile||X|X|X|
|Элемент управления ActiveX библиотеки MFC|||X|X|
|Приложение MFC|||X|X|
|Библиотека DLL MFC|||X|X|
|Тестовый проект|X|X|X|X|
|Консольное приложение Win32||X|X|X|
|Проект Win32||X|X|X|

## <a name="tools"></a>Инструменты

|Средство|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Инкрементный компоновщик (Link.exe)|X|X|X|X|
|Служебная программа обслуживания программ (Nmake.exe)||X|X|X|
|Генератор библиотек (Lib.exe)|X|X|X|X|
|Компилятор ресурсов Windows (Rc.exe)|X|X|X|X|
|Конвертер ресурсов Windows в объекты (CvtRes.exe)||X|X|X|
|Служебная программа Browse Information Maintenance (BscMake.exe)|X|X|X|X|
|C++ Name Undecorator (Undname.exe)|X|X|X|X|
|COFF/PE Dumper (Dumpbin.exe)|X|X|X|X|
|COFF/PE Editor (Editbin.exe)|X|X|X|X|
|MASM (Ml.exe)|||X|X|
|Spy++|||X|X|
|ErrLook|||X|X|
|AtlTrace|||X|X|
|Devenv.com|||X|X|
|Правила вывода|||X|X|
|Обновление проектов VCBuild с расширением VCPROJ до MSBuild (VCUpgrade.exe)|X|X|X|X|
|Оптимизация с использованием профиля|||X|X|

## <a name="debugging-features"></a>Средства отладки

|Средство отладки|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Отладка машинного кода|X|X|X|X|
|natvis (визуализация собственного типа)|X|X|X|X|
|Отладка графики|X||X|X|
|Отладка управляемого кода||X|X|X|
|Использование GPU|X||X|X|
|Использование памяти|X||X|X|
|Remote Debugging|X|X|X|X|
|Отладка SQL|||X|X|
|Статический анализ кода|Ограниченный|Ограниченный|X|X|

## <a name="designers-and-editors"></a>Редакторы и конструкторы

|Редактор или конструктор|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Конструктор XAML|X||X|X|
|Конструктор и редактор стилей CSS|X|X|X|X|
|Конструктор и редактор HTML|X|X|X|X|
|XML-редактор|X|X|X|X|
|Редактор исходного кода|X|X|X|X|
|Возможности повышения производительности: рефакторинг, IntelliSense, форматирование кода C++|X|X|X|X|
|Конструктор Windows Forms||X|X|X|
|Конструктор данных|||X|X|
|Собственный редактор ресурсов (RC-файлы)|||X|X|
|редакторы ресурсов|X|X|X|X|
|Редактор моделей|X||X|X|
|Конструктор шейдеров|X||X|X|

## <a name="data-features"></a>Средства работы с данными

|Средство работы с данными|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Конструктор данных|||X|X|
|Объекты данных|||X|X|
|Веб-службы|||X|X|
|обозревателя серверов|||X|X|

## <a name="build-and-project-systems"></a>Системы сборки и проектов

|Функция сборки или проекта|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Построение с помощью командной строки (msbuild.exe)|X|X|X|X|
|Собственное многоплатформенное нацеливание||X|X|X|
|Управляемое многоплатформенное нацеливание||X|X|X|
|Параллельное построение|X|X|X|X|
|Настройки сборки|X|X|X|X|
|Расширяемость страниц свойств|X|X|X|X|

## <a name="automation-and-extensibility"></a>Автоматизация и расширяемость

|Автоматизация и расширяемость|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Объектные модели расширения среды|||X|X|
|Модель кода|||X|X|
|модель проекта|||X|X|
|Модель редактора ресурсов|||X|X|
|Модель мастера|||X|X|
|Объектная модель отладчика|||X|X|

## <a name="application-lifecycle-management-tools"></a>Средства управления жизненным циклом приложения

||||||
|-|-|-|-|-|
|Средство|Visual Studio Express для Windows|Visual Studio Express для Windows Desktop|Visual Studio Professional и Community|Visual Studio Enterprise|
|Модульное тестирование (собственная платформа)|X|X|X|X|
|Модульное тестирование (управляемая платформа)||X|X|X|
|Покрытие кода||||X|
|Тестирование вручную||||X|
|Произвольное тестирование||||X|
|Управление тестовыми случаями||||X|
|Карта кода и диаграммы зависимостей|||только для чтения|X|
|Отладка карты кода||||X|

## <a name="see-also"></a>См. также

[Установка Visual Studio](/visualstudio/install/install-visual-studio)<br/>
[Новые возможности Visual Studio](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Типы проектов C++ в Visual Studio](../build/reference/visual-cpp-project-types.md)

::: moniker-end
