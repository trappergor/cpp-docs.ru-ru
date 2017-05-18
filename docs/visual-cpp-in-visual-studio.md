---
title: "Visual C++ в Visual Studio | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- visual c++
- visual c
- vc
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: da3c2e6ce7247d3e8c9a401bc0a133cb8d46a970
ms.openlocfilehash: 81a7d724a4a3b2e5aa7de47461d20cc3385896eb
ms.contentlocale: ru-ru
ms.lasthandoff: 03/15/2017

---
# <a name="visual-c-in-visual-studio"></a>Visual C++ в Visual Studio
Язык программирования в Visual Studio 2017 и средства разработки позволяют разрабатывать универсальные приложения Windows неуправляемого кода, классические и серверные приложения неуправляемого кода, межплатформенные библиотеки для Android, iOS и Windows, а также управляемые приложения, работающие на платформе .NET Framework.  
  
 **Для кого предназначена эта документация?**  
  
 Этот материал предназначен для разработчиков на C++, создающих программы.  
  
-   Если вам нужен определенный распространяемый пакет C++ и компоненты среды выполнения для запуска программы, перейдите в [Центр загрузки Майкрософт](http://www.microsoft.com/en-us/download/) и введите в поле поиска **Visual C++** .  
  
-   Если вы хотите ознакомиться с принципами программирования на C++, перейдите на один из множества соответствующих ресурсов или приобретите книгу [Programming — Principles and Practice Using C++ (Second Edition)](http://stroustrup.com/Programming/) (Программирование: принципы и практика использования C++, изд.&2;), которую написал создатель языка C++ Бьёрн Страуструп (Bjarne Stroustrup). В материалах по Visual C++ предполагается, что у вас уже есть базовые знания о C++.  
  
-   Если вам необходим компилятор Visual C++, необходимо скачать платную или бесплатную версию Visual Studio на сайте [https://www.visualstudio.com/](https://www.visualstudio.com/).  

## <a name="general-information-about-visual-c"></a>Общие сведения о Visual C++  
 [Новые возможности Visual C++](what-s-new-for-visual-cpp-in-visual-studio.md)  
 Новые возможности Visual C++.  

 [Улучшения соответствия C++ в Visual Studio 2017](cpp-conformance-improvements-2017.md) 
 Узнайте об улучшениях соответствия C++ в Visual Studio 2017. 

 [Соответствие стандартам языка Visual C++](visual-cpp-language-conformance.md)  
 Список с данными о состоянии соответствия стандартам по каждой функции в Visual C++.

 [Журнал изменений Visual C++ 2003–2015](porting/visual-cpp-change-history-2003-2015.md)  
 Ознакомьтесь с критическими изменениями в предыдущих версиях.  
  
 [Возвращение к C++](cpp/welcome-back-to-cpp-modern-cpp.md)  
 Дополнительные сведения о современных методах программирования на C++ на основе C ++&11; и C ++&14; для написания быстродействующего и безопасного кода и исключения многих типичных ошибок программирования в стиле C.  
  
 [Как сообщить о проблеме с набором инструментов Visual C++](how-to-report-a-problem-with-the-visual-cpp-toolset.md)  
 Сведения о создании эффективных отчетов об ошибках с использованием набора инструментов Visual C++ (компилятора, компоновщика и других средств) и информация о способах отправки отчета.  
  
 [Руководство по переносу и обновлению Visual C++](porting/visual-cpp-porting-and-upgrading-guide.md)  
 Руководство по переносу кода и обновлению проектов для Visual C++ в Visual Studio 2017, включая перенос кода C++ в Windows 10 и универсальную платформу Windows.  
  
 [Блог команды разработчиков Visual C++](http://blogs.msdn.com/b/vcblog/)  
 Описание новых возможностей и актуальная информация от разработчиков [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)].  
  
 [Загружаемые файлы Visual Studio](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Загрузка Visual C++.  
  
 [Инструменты и функции Visual C++ в выпусках Visual Studio](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)  
 Сведения о разных редакциях Visual C++.  
  
 [Поддерживаемые платформы](supported-platforms-visual-cpp.md)  
 Поддерживаемые платформы.  
  
 [Примеры кода на Visual C++](visual-cpp-samples.md)  
 Информация о примерах.  
  
 [Visual Studio Community](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Обращение за помощью, регистрация ошибок и предложения по Visual Studio.  
  
## <a name="writing-applications-in-c"></a>Создание приложений на языке C++  
 [Универсальные приложения Windows](windows/universal-windows-apps-cpp.md)  
 Руководства и справочные материалы в Центре разработчика Windows. Дополнительные сведения о разработке приложений для Магазина Windows см. в разделе [Разработка приложений для Магазина Windows с помощью Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=248364) и [Схема создания приложений для Магазина Windows на С++](http://go.microsoft.com/fwlink/p/?LinkId=244654).  
  
 [Классические приложения (Visual C++)](windows/desktop-applications-visual-cpp.md)  
 Создание классических приложений, включающих цикл обработки сообщений и обратные вызовы.  
  
 [DLL в Visual C++](build/dlls-in-visual-cpp.md)  
 Использование Win32, ATL и MFC для создания классических библиотек DLL для Windows, а также сведения о компиляции и регистрации библиотеки DLL.  
  
 [Параллельное программирование](parallel/parallel-programming-in-visual-cpp.md)  
 Использование библиотеки параллельных шаблонов, C++ AMP, OpenMP и другим компонентов, связанных с многопоточностью в Windows.  
  
 [Рекомендации по безопасности](security/security-best-practices-for-cpp.md)  
 Защита приложений от вредоносного кода и несанкционированного использования.  
  
 [Облачное и веб-программирование](cloud/cloud-and-web-programming-in-visual-cpp.md)  
 В C++ имеются несколько параметров для соединения с веб-узлом и облаком.  
  
 [Доступ к данным](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b)  
 Для подключения к базам данных используйте ODBC и другие технологии доступа к базам данных.  
  
 [Текст и строки](text/text-and-strings-in-visual-cpp.md)  
 Подробнее о работе с другими форматами текста и строк и кодировках для локальных и международных разработок.  
  
## <a name="c-development-tools"></a>Средства разработки C++  
 Дополнительные сведения о создании проектов, работе с файлами исходного кода, ссылках на библиотеки, компиляции, отладке, профилировании, развертывании и т. д. см. в статье [Интегрированная среда разработки и средства разработки Visual C++](ide/ide-and-tools-for-visual-cpp-development.md).  
  
## <a name="c-language-reference"></a>Справочник по языку C++  
 Сведения о языке C++ см. в статье [правочник по языку C++](cpp/cpp-language-reference.md).  
  
 Сведения о препроцессоре C++ см. в статье [Справочник по препроцессору C/C++](preprocessor/c-cpp-preprocessor-reference.md).  
  
## <a name="c-libraries-in-visual-studio"></a>Библиотеки C++ в Visual Studio  
 В следующих разделах приведены сведения о различных библиотеках C++, включенных в Visual C++.  
  
 [Справочник по библиотеке времени выполнения C](c-runtime-library/c-run-time-library-reference.md)  
 Включает альтернативы с улучшенной безопасностью для функций, которые, как известно, могут представлять угрозу безопасности.  
  
 [Стандартная библиотека C++](standard-library/cpp-standard-library-reference.md)  
 Стандартная библиотека C++.  
  
 [Библиотека шаблонных классов (ATL)](atl/atl-com-desktop-components.md)  
 Поддержка компонентов и приложений COM.  
  
 [Библиотеки Microsoft Foundation Class (MFC)](mfc/mfc-desktop-applications.md)  
 Поддержка создания классических приложений с традиционными пользовательскими интерфейсами или интерфейсами в стиле Office.  
  
 [Библиотека параллельных шаблонов (PPL)](parallel/concrt/parallel-patterns-library-ppl.md)  
 Асинхронные и параллельные алгоритмы, выполняемые в ЦП.  
  
 [C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 Массово-параллельные алгоритмы, выполняемые в GPU.  
  
 [Библиотека шаблонов среды выполнения Windows (WRL)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
Приложения и компоненты  [!INCLUDE[win8_appname_long](build/includes/win8_appname_long_md.md)].  
  
 [Программирование .NET с использованием C++/CLI (Visual C++)](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 Программирование для общеязыковой среды выполнения (CLR).  
  
 См. также документацию по [STL/CLR](dotnet/stl-clr-library-reference.md) и [библиотеке поддержки C++](dotnet/cpp-support-library.md).  
  
## <a name="other-c-libraries"></a>Другие библиотеки C++  
 Этот раздел содержит ссылки на библиотеки, которые не входят в состав Visual Studio, но доступны для загрузки и использования с Visual C++.  
  
 [Boost](http://www.boost.org/)  
 Популярная и широко распространенная библиотека.  
  
 [C++ REST SDK](http://casablanca.codeplex.com).  
 Библиотека Microsoft для взаимодействия с веб-службами по протоколу HTTP.  
  
## <a name="more-resources"></a>Дополнительные ресурсы  
 [Ресурсы, посвященные Visual C++](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Дополнительные ресурсы информации по Visual C++.  
  
 [Стандартный C++](http://isocpp.org/)  
 Дополнительные сведения о C++, обзор Modern C++ и ссылки на книги, статьи, обсуждения и данные о событиях  
  
 [Знакомство с Visual C++](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Начало изучения C++.  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C](c-language/c-language-reference.md)   
 [Справочник по библиотеке времени выполнения C](c-runtime-library/c-run-time-library-reference.md)   
 [Внутренние объекты компилятора и язык ассемблера](intrinsics/compiler-intrinsics-and-assembly-language.md)

