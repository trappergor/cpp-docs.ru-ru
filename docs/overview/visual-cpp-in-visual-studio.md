---
title: C++ в Visual Studio
description: Под Visual C++ подразумевается компилятор Microsoft C++, редактор кода и связанные инструменты в Интегрированной среде разработки Visual Studio. Используйте Visual C++ для разработки программ для Windows, Linux, Android и iOS.
ms.date: 09/26/2018
ms.technology: cpp-ide
helpviewer_keywords:
- Visual C++, home page
author: mikeblome
ms.author: mblome
ms.openlocfilehash: a01c6448174a35da900b7b50a1df5916a2983201
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222602"
---
# <a name="c-in-visual-studio"></a>C++ в Visual Studio

> [!NOTE]
> Эта документация для разработчиков применима к Visual Studio 2015 и Visual Studio 2017.
>
> Если вам нужен определенный распространяемый пакет Visual C++ для запуска программы, перейдите в [Центр загрузки Майкрософт](http://www.microsoft.com/download/) и введите в поле поиска **Visual C++**.


Microsoft Visual C++ (обычно сокращают до Visual C++ или MSVC) является названием для библиотек и средств разработки на языке ассемблера, C++ и C, входящих в состав Visual Studio в Windows. Эти средства и библиотеки позволяют создавать приложения универсальной платформы Windows (UWP), собственные классические и серверные приложения Windows, кроссплатформенные библиотеки и приложения для Windows, Linux, Android и iOS, а также управляемые приложения и библиотеки, использующие платформу .NET Framework. С помощью Visual C++ можно разработать что угодно — от простых консольных приложений до самых сложных приложений для настольных систем Windows, от драйверов устройств и компонентов операционной системы до кроссплатформенных игр для мобильных устройств и от мельчайших устройств Интернета вещей до многосерверных высокопроизводительных вычислительных систем в облаке Azure.

## <a name="whats-new-and-conformance-history"></a>Новые возможности и журнал соответствий

[Новые возможности C++ в Visual Studio](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
Новые возможности в Visual Studio.

[Новые возможности C++ в версиях Visual Studio с 2003 до 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
Новые возможности C++ для каждой версии Visual Studio с 2003 до 2015.

[Улучшения соответствия C++ в Visual Studio](cpp-conformance-improvements.md)<br/>
Сведения об улучшениях соответствия C++ в Visual Studio.

[Соответствие стандартам языка Visual C++](visual-cpp-language-conformance.md)<br/>
Список с данными о состоянии соответствия стандартам по каждой функции в компиляторе C++ MSVC.

[Журнал изменений Visual C++ 2003–2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
Ознакомьтесь с критическими изменениями в предыдущих версиях.

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Установка Visual Studio и обновление с более ранних версий

[Установка поддержки С++ в Visual Studio](../build/vscpp-step-0-installation.md)<br/>
Скачайте Visual Studio 2015 или Visual Studio 2017 и установите набор инструментов Visual C++.

[Руководство по переносу и обновлению Visual C++](../porting/visual-cpp-porting-and-upgrading-guide.md)<br/>
Руководство по переносу кода и обновлению проектов для Visual Studio 2015 или Visual Studio 2017, включая перенос кода C++ в Windows 10 и универсальную платформу Windows.

[Инструменты и функции Visual C++ в выпусках Visual Studio](visual-cpp-tools-and-features-in-visual-studio-editions.md)<br/>
Сведения о разных редакциях Visual C++.

[Поддерживаемые платформы](supported-platforms-visual-cpp.md)<br/>
Поддерживаемые платформы.

## <a name="learn-c"></a>Знакомство с C++

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
Дополнительные сведения о современных методах программирования на C++ на основе C ++ 11 и C ++ 14 для написания быстродействующего и безопасного кода и исключения многих типичных ошибок программирования в стиле C.

[Стандартная C++](http://isocpp.org/)<br/>
Дополнительные сведения о C++, обзор Modern C++ и ссылки на книги, статьи, обсуждения и данные о событиях

[Знакомство с Visual C++](../build/vscpp-step-1-create.md)<br/>
Начало изучения C++.

[Примеры кода на Visual C++](visual-cpp-samples.md)<br/>
Информация о примерах.

## <a name="c-development-tools"></a>Средства разработки C++

[Разработка приложений C++ в Visual Studio](overview-of-cpp-development.md)<br/>
Использование интегрированной среды разработки Visual Studio для создания проектов, редактирования кода, создания ссылок на библиотеки, компиляции, отладки, создания модульных тестов, выполнения статического анализа, развертывания и многого другого.

[Проекты и системы сборки](../build/projects-and-build-systems-cpp.md)<br/>
Как создать и настроить проекты Visual Studio C++, проекты CMake и другие типы проектов с помощью компилятора MSVC и параметров компоновщика.

[Написание и рефакторинг кода C++](../ide/writing-and-refactoring-code-cpp.md)<br/>
Как использовать функции производительности в редакторе C++ для рефакторинга и написания кода и перемещения по нему.

[Отладка машинного кода](/visualstudio/debugger/debugging-native-code)<br/>
Сведения об использовании отладчика Visual Studio с проектами C++.

[Общие сведения об анализе кода на C и C++](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)<br/>
Используйте заметки SAL или средства проверки C++ Core Guidelines для выполнения статического анализа.

[Написание модульных тестов для C/C++ в Visual Studio](/visualstudio/test/writing-unit-tests-for-c-cpp)<br/>
Создание модульных тестов с помощью платформы модульного тестирования Майкрософт для C++, Google Test, Boost.Test или CTest.

## <a name="write-applications-in-c"></a>Создание приложений на C++

[Универсальные приложения Windows](../windows/universal-windows-apps-cpp.md)<br/>
Руководства и справочные материалы в Центре разработчика Windows. Сведения о разработке приложений UWP см. в разделах [Введение в универсальную платформу Windows](/windows/uwp/get-started/universal-application-platform-guide) и [Создание первого приложения UWP на C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

[Классические приложения (C++)](../windows/desktop-applications-visual-cpp.md)<br/>
Сведения о создании классических приложений с машинным кодом на C++ для Windows.

[Программирование .NET с использованием C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
Сведения о создании библиотек DLL, обеспечивающих взаимодействие между машинным кодом на C++ и программами .NET, написанными на таких языках, как C# или Visual Basic.

[Программирование на Linux](../linux/index.md)<br/>
Интегрированная среда разработки Visual Studio позволяет написать код и развернуть его на удаленном компьютере с ОС Linux для компиляции с помощью GCC.

[Создание библиотек DLL C/C++ в Visual Studio](../build/dlls-in-visual-cpp.md)<br/>
Использование Win32, ATL и MFC для создания классических библиотек DLL для Windows, а также сведения о компиляции и регистрации библиотеки DLL.

[Параллельное программирование](../parallel/parallel-programming-in-visual-cpp.md)<br/>
Использование библиотеки параллельных шаблонов, C++ AMP, OpenMP и другим компонентов, связанных с многопоточностью в Windows.

[Рекомендации по безопасности](../security/security-best-practices-for-cpp.md)<br/>
Защита приложений от вредоносного кода и несанкционированного использования.

[Облачное и веб-программирование](../cloud/cloud-and-web-programming-in-visual-cpp.md)<br/>
В C++ имеются несколько параметров для соединения с веб-узлом и облаком.

[Доступ к данным](../data/data-access-in-cpp.md)<br/>
Для подключения к базам данных используйте ODBC и другие технологии доступа к базам данных.

[Текст и строки](../text/text-and-strings-in-visual-cpp.md)<br/>
Подробнее о работе с другими форматами текста и строк и кодировках для локальных и международных разработок.

## <a name="languages-reference"></a>Справочники по языкам

[Справочник по языку C++](../cpp/cpp-language-reference.md)

[Справочник по препроцессору в C/C++](../preprocessor/c-cpp-preprocessor-reference.md)

[Справочник по языку C#](../c-language/c-language-reference.md)

[Внутренние объекты компилятора и язык ассемблера](../intrinsics/compiler-intrinsics-and-assembly-language.md)

## <a name="c-libraries-in-visual-studio"></a>Библиотеки C++ в Visual Studio

В следующих разделах приведены сведения о различных библиотеках C и C++, включенных в Visual Studio.

[Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)<br/>
Включает альтернативы с улучшенной безопасностью для функций, которые, как известно, могут представлять угрозу безопасности.

[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)<br/>
Стандартная библиотека C++.

[Библиотека шаблонных классов (ATL)](../atl/atl-com-desktop-components.md)<br/>
Поддержка компонентов и приложений COM.

[Библиотеки Microsoft Foundation Class (MFC)](../mfc/mfc-desktop-applications.md)<br/>
Поддержка создания классических приложений с традиционными пользовательскими интерфейсами или интерфейсами в стиле Office.

[Библиотека параллельных шаблонов (PPL)](../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Асинхронные и параллельные алгоритмы, выполняемые в ЦП.

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
Массово-параллельные алгоритмы, выполняемые в GPU.

[Библиотека шаблонов среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)<br/>
Приложения и компоненты универсальной платформы Windows (UWP).

[Программирование .NET с использованием C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
Программирование для общеязыковой среды выполнения (CLR).

## <a name="third-party-open-source-c-libraries"></a>Сторонние библиотеки C++ с открытым исходным кодом

Кроссплатформенная программа командной строки **vcpkg** значительно упрощает обнаружение и установку более чем 900 библиотек C++ с открытым исходным кодом. См. раздел [vcpkg: диспетчер пакетов C++ для Windows](../build/vcpkg.md).

## <a name="feedback-and-community"></a>Обратная связь и сообщество

[Как сообщить о проблеме с набором инструментов Visual C++](how-to-report-a-problem-with-the-visual-cpp-toolset.md)<br/>
Сведения о создании эффективных отчетов об ошибках с использованием набора инструментов Visual C++ (компилятора, компоновщика и других средств) и информация о способах отправки отчета.

[Блог группы разработчиков Microsoft по C++](https://devblogs.microsoft.com/cppblog/)<br/>
Описание новых возможностей и актуальная информация от разработчиков инструментов C++ в Visual Studio.

[Сообщество разработчиков Visual Studio](https://developercommunity.visualstudio.com/)<br/>
Обращение за помощью, регистрация ошибок и предложения по Visual Studio.

## <a name="see-also"></a>См. также

- [Справочник по языку C#](../c-language/c-language-reference.md)
- [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)
- [Внутренние объекты компилятора и язык ассемблера](../intrinsics/compiler-intrinsics-and-assembly-language.md)
