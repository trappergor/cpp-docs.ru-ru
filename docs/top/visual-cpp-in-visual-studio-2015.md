---
title: "Visual C++ в Visual Studio&#160;2015 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "visual c++"
  - "visual c"
  - "vc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "неуправляемый код, C++"
  - "среда разработки, Visual C++"
  - "неуправляемый код"
  - "Visual C++"
  - "Visual C++, справочник"
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
caps.handback.revision: 61
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ в Visual Studio&#160;2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Язык программирования [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] и средства разработки позволяют разрабатывать универсальные приложения Windows неуправляемого кода, классические и серверные приложения неуправляемого кода, межплатформенные библиотеки для Android, iOS и Windows, а также управляемые приложения, работающие на платформе .NET Framework.  
  
 **Для кого предназначена эта документация?**  
  
 Этот материал предназначен для разработчиков на C\+\+, создающих программы.  
  
-   Если вам нужен определенный распространяемый пакет C\+\+ и компоненты среды выполнения для запуска программы, перейдите в [Центр загрузки Майкрософт](http://www.microsoft.com/en-us/download/) и введите в поле поиска **Visual C\+\+**.  
  
-   Если вы хотите ознакомиться с принципами программирования на C\+\+, перейдите на один из множества соответствующих ресурсов или приобретите книгу [Programming — Principles and Practice Using C\+\+ \(Second Edition\)](http://stroustrup.com/Programming/) \(Программирование: принципы и практика использования C\+\+, изд. 2\), которую написал создатель языка C\+\+ Бьёрн Страуструп \(Bjarne Stroustrup\). В материалах по Visual C\+\+ предполагается, что у вас уже есть базовые знания о C\+\+.  
  
-   Если вам необходим компилятор Visual C\+\+, необходимо скачать платную или бесплатную версию Visual Studio 2015 на сайте [https:\/\/www.visualstudio.com\/](https://www.visualstudio.com/).  
  
> [!WARNING]
>  В Visual Studio 2015 Visual C\+\+ не устанавливается по умолчанию. При установке следует выбрать **выборочный** вариант установки, а затем выбрать нужные компоненты C\+\+. Или, если среда Visual Studio уже установлена, выберите **Файл\/Создать\/Проект\/C\+\+**, после чего будет выведено предложение установить необходимые компоненты.  
  
## Общие сведения о Visual C\+\+  
 [Новые возможности Visual C\+\+](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)  
 Новые возможности Visual C\+\+.  
  
 [Критические изменения в Visual C\+\+ 2015](../Topic/Visual%20C++%20change%20history%202003%20-%2020151.md)  
 Критические изменения в данной версии.  
  
 [Возвращение к C\+\+](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)  
 Дополнительные сведения о современных методах программирования на C\+\+ на основе C \+\+ 11 и C \+\+ 14 для написания быстродействующего и безопасного кода и исключения многих типичных ошибок программирования в стиле C.  
  
 [How to Report a Problem with the Visual C\+\+ Toolset](../Topic/How%20to%20Report%20a%20Problem%20with%20the%20Visual%20C++%20Toolset.md)  
 Сведения о создании эффективных отчетов об ошибках с использованием набора инструментов Visual C\+\+ \(компилятора, компоновщика и других средств\) и информация о способах отправки отчета.  
  
 [Руководство по переносу и обновлению Visual C\+\+](../porting/visual-cpp-porting-and-upgrading-guide.md)  
 Руководство по переносу кода и обновлению проектов для Visual C\+\+ в [!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)], включая перенос кода C\+\+ в Windows 10 и универсальную платформу Windows.  
  
 [Поддержка возможностей C\+\+ 11\/14\/17](../Topic/Support%20For%20C++11-14-17%20Features%20\(Modern%20C++\).md)  
 Подробнее о поддержке возможностей C\+\+11 и С\+\+14 в Visual C\+\+.  
  
 [Блог команды разработчиков Visual C\+\+](http://blogs.msdn.com/b/vcblog/)  
 Описание новых возможностей и актуальная информация от разработчиков [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
 [Загружаемые файлы Visual Studio](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Загрузка Visual C\+\+.  
  
 [Инструменты и шаблоны Visual C\+\+ в выпусках Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)  
 Сведения о разных редакциях Visual C\+\+.  
  
 [Поддерживаемые платформы](../top/supported-platforms-visual-cpp.md)  
 Поддерживаемые платформы.  
  
 [Примеры кода на Visual C\+\+](../top/visual-cpp-samples.md)  
 Информация о примерах.  
  
 [Visual Studio Community](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Обращение за помощью, регистрация ошибок и предложения по Visual Studio.  
  
## Создание приложений на языке C\+\+  
 [Универсальные приложения Windows](../windows/universal-windows-apps-cpp.md)  
 Руководства и справочные материалы в Центре разработчика Windows. Дополнительные сведения о разработке приложений для Магазина Windows см. в разделе [Разработка приложений для Магазина Windows с помощью Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=248364) и [Схема создания приложений для Магазина Windows на С\+\+](http://go.microsoft.com/fwlink/p/?LinkId=244654).  
  
 [Классические приложения Windows \(Visual C\+\+\)](../windows/desktop-applications-visual-cpp.md)  
 Создание классических приложений, включающих цикл обработки сообщений и обратные вызовы.  
  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)  
 Использование Win32, ATL и MFC для создания классических библиотек DLL для Windows, а также сведения о компиляции и регистрации библиотеки DLL.  
  
 [Параллельное программирование](../parallel/parallel-programming-in-visual-cpp.md)  
 Использование библиотеки параллельных шаблонов, C\+\+ AMP, OpenMP и другим компонентов, связанных с многопоточностью в Windows.  
  
 [Рекомендации по безопасности](../top/security-best-practices-for-cpp.md)  
 Защита приложений от вредоносного кода и несанкционированного использования.  
  
 [Облачное и веб\-программирование](../Topic/Cloud%20and%20Web%20Programming%20in%20Visual%20C++.md)  
 В C\+\+ имеются несколько параметров для соединения с веб\-узлом и облаком.  
  
 [Доступ к данным](../Topic/Data%20Access%20in%20Visual%20C++.md)  
 Для подключения к базам данных используйте ODBC и другие технологии доступа к базам данных.  
  
 [Текст и строки](../text/text-and-strings-in-visual-cpp.md)  
 Подробнее о работе с другими форматами текста и строк и кодировках для локальных и международных разработок.  
  
## Средства разработки C\+\+  
 Дополнительные сведения о создании проектов, работе с файлами исходного кода, ссылках на библиотеки, компиляции, отладке, профилировании, развертывании и т. д. см. в разделе [Интегрированная среда разработки и средства разработки](../Topic/IDE%20and%20Tools%20for%20Visual%20C++%20Development.md).  
  
## Справочник по языку C\+\+  
 Сведения о языке C\+\+ см. в документе [Справочник по языку C\+\+](../cpp/cpp-language-reference.md).  
  
 Сведения о препроцессоре C\+\+ см. в документе [Справочник по препроцессору C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md).  
  
## Библиотеки C\+\+ в Visual Studio  
 В следующих разделах приведены сведения о различных библиотеках C\+\+, включенных в Visual C\+\+.  
  
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)  
 Включает альтернативы с улучшенной безопасностью для функций, которые, как известно, могут представлять угрозу безопасности.  
  
 [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md)  
 Библиотека стандартных шаблонов \(STL\).  
  
 [Библиотека шаблонных классов \(ATL\)](../atl/atl-com-desktop-components.md)  
 Поддержка компонентов и приложений COM.  
  
 [Библиотеки Microsoft Foundation Class \(MFC\)](../mfc/mfc-desktop-applications.md)  
 Поддержка создания классических приложений с традиционными пользовательскими интерфейсами или интерфейсами в стиле Office.  
  
 [Библиотека параллельных шаблонов](../parallel/concrt/parallel-patterns-library-ppl.md)  
 Асинхронные и параллельные алгоритмы, выполняемые в ЦП.  
  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 Массово\-параллельные алгоритмы, выполняемые в GPU.  
  
 [Библиотека шаблонов среды выполнения Windows \(WRL\)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 Приложения и компоненты [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  
  
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 Программирование для общеязыковой среды выполнения \(CLR\).  
  
 См. также документацию по [STL\/CLR](../dotnet/stl-clr-library-reference.md) и [Библиотека поддержки C\+\+](../dotnet/cpp-support-library.md).  
  
## Другие библиотеки C\+\+  
 Этот раздел содержит ссылки на библиотеки, которые не входят в состав Visual Studio, но доступны для загрузки и использования с Visual C\+\+.  
  
 [Boost](http://www.boost.org/)  
 Популярная и широко распространенная библиотека.  
  
 [C\+\+ REST SDK](http://casablanca.codeplex.com).  
 Библиотека Microsoft для взаимодействия с веб\-службами по протоколу HTTP.  
  
## Дополнительные ресурсы  
 [Ресурсы, посвященные Visual C\+\+](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Дополнительные ресурсы информации по Visual C\+\+.  
  
 [Стандартная C\+\+](http://isocpp.org/)  
 Дополнительные сведения о C\+\+, обзор Modern C\+\+ и ссылки на книги, статьи, обсуждения и данные о событиях  
  
 [Знакомство с Visual C\+\+](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Начало изучения C\+\+.  
  
## См. также  
 [Справочник по языку C](../Topic/C%20Language%20Reference.md)   
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)   
 [Внутренние объекты компилятора и язык ассемблера](../intrinsics/compiler-intrinsics-and-assembly-language.md)