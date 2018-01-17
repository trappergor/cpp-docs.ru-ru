---
title: "Пошаговое руководство: Создание традиционных приложений для Windows Desktop (C++) | Документы Microsoft"
ms.custom: 
ms.date: 1/11/2018
ms.reviewer: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3c18abbace2181b2d31e0621b6e376021be68a
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2018
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Пошаговое руководство: Создание традиционных приложений для Windows Desktop (C++)

В этом пошаговом руководстве демонстрируется создание традиционных приложений для настольных компьютеров Windows в Visual Studio. Пример приложения, который вы создаете использует Windows API для отображения «Hello, рабочий стол Windows!» "Hello, World!". Код, созданный в этом пошаговом руководстве, можно использовать в качестве шаблона для создания других классических приложений Windows.

API Windows (также известный как API-интерфейса Win32, API рабочего стола Windows и классический API Windows) — это платформа на основе языка C для создания приложений Windows. Он был еще 1980 в ОС и используется для создания приложений Windows для десятилетия. Расширенные и простой программы платформы созданы поверх этот API, например MFC, ATL и .NET frameworks. Даже самые современные код UWP и хранилище приложений, написанных на C + +/ WinRT используют этот интерфейс API под. Дополнительные сведения о формате Windows API см. в разделе [индекс API Windows](https://msdn.microsoft.com/library/windows/desktop/ff818516.aspx). Существует много способов создания приложений Windows, но это был первый.

> [!IMPORTANT]
> Для краткости опущены некоторые операторы кода, в тексте. [Сборку кода](#build-the-code) в конце этого документа показан полный код.

## <a name="prerequisites"></a>Предварительные требования

- На компьютере под управлением Microsoft Windows 7 или более поздней версии. Для получения наилучших результатов разработки мы рекомендуем Windows 10.

- Копия Visual Studio 2017 г. Сведения о том, как загрузить и установить Visual Studio см. в разделе [установить Visual Studio 2017](/visualstudio/install/install-visual-studio). При запуске программы установки, убедитесь, что **разработки настольных приложений с помощью C++** проверяется рабочей нагрузки. Не беспокойтесь, если рабочая нагрузка не установлен, при установке Visual Studio. Можно еще раз запустите программу установки и установите его.

   ![Для разработки настольных приложений с помощью C++](../build/media/desktop-development-with-cpp.png "разработки настольных приложений на C++")

- Основные сведения о основные принципы использования интегрированной среды разработки Visual Studio. При использовании классических приложений Windows, прежде чем вы, вероятно, справляется. Вводные сведения см. в разделе [Обзор возможностей Visual Studio IDE](/visualstudio/ide/visual-studio-ide).

- Понимание достаточно работы необходимо владеть основами языка C++ для выполнения этой процедуры. Не беспокойтесь, мы не предпринимать слишком сложное.

## <a name="create-a-windows-desktop-project"></a>Создание проекта рабочего стола Windows

Выполните следующие действия для создания вашего первого проекта рабочего стола Windows и введите код для работы приложений рабочего стола Windows. Если вы используете версию Visual Studio более ранней, чем версия 15,3 2017 г. Visual Studio, перейдите к [для создания проекта классического приложения Windows в Visual Studio RTM 2017 г](#create-in-vs2017-rtm).

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Создание проекта рабочего стола Windows в Visual Studio 2017 г. обновление 15,3 и более поздних версий

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В **новый проект** разверните на левой панели окна **установленные**, **Visual C++**, а затем выберите **Windows Desktop**. В средней области выберите **мастер рабочего стола Windows**.

   В **имя** введите имя проекта, например, *DesktopApp*. Нажмите кнопку **ОК**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-153.png "имя проекта DesktopApp")

1. В **проект рабочего стола Windows** диалогового окна в разделе **тип приложения**выберите **приложения Windows (.exe)**. В поле **Дополнительные параметры**выберите **Пустой проект**. Выберите **ОК** для создания проекта.

   ![Создайте DesktopApp в мастере проекта классического приложения Windows](../build/media/desktop-app-new-project-wizard-153.png "создайте DesktopApp в мастере проекта классического приложения Windows")

1. В **обозревателе решений**, щелкните правой кнопкой мыши **DesktopApp** проекта, выбор **добавить**, а затем выберите **новый элемент**.

   ![Добавить новый элемент к проекту DesktopApp](../build/media/desktop-app-project-add-new-item-153.gif "добавить новый элемент к проекту DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В **имя** введите имя файла, например, *HelloWindowsDesktop.cpp*. Выберите **Добавить**.

   ![Добавить CPP-файл к проекту DesktopApp](../build/media/desktop-app-add-cpp-file-153.png "добавить CPP-файл к проекту DesktopApp")

Теперь создается проект и открывается в редакторе исходного файла. Чтобы продолжить, перейдите к [создания кода](#create-the-code).

### <a id="create-in-vs2017-rtm"></a>Создание проекта классического приложения Windows в Visual Studio RTM 2017 г.

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В **новый проект** разверните в левой области диалогового **установленные**, **шаблоны**, **Visual C++**, а затем выберите **Win32**. В средней области выберите шаблон **Проект Win32**.

   В **имя** введите имя проекта, например, *DesktopApp*. Нажмите кнопку **ОК**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-150.png "имя проекта DesktopApp")

1. На **Обзор** страница **мастер приложений Win32**, выберите **Далее**.

   ![Создание DesktopApp в общие сведения о мастере приложения Win32](../build/media/desktop-app-win32-wizard-overview-150.png "создать DesktopApp в общие сведения о мастере приложения Win32")

1. На **параметры приложения** в разделе **тип приложения**выберите **приложение Windows**. В поле **Дополнительные параметры**выберите **Пустой проект**. Выберите **Готово** для создания проекта.

   ![Создание DesktopApp в параметры мастера приложений Win32](../build/media/desktop-app-win32-wizard-settings-150.png "создать DesktopApp в параметры мастера приложений Win32")

1. В **обозреватель решений**, щелкните правой кнопкой мыши проект DesktopApp, выберите **добавить**, а затем выберите **новый элемент**.

   ![Добавить новый элемент к проекту DesktopApp](../build/media/desktop-app-project-add-new-item-150.gif "добавить новый элемент к проекту DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В **имя** введите имя файла, например, *HelloWindowsDesktop.cpp*. Выберите **Добавить**.

   ![Добавить CPP-файл к проекту DesktopApp](../build/media/desktop-app-add-cpp-file-150.png "добавить CPP-файл к проекту DesktopApp")

Теперь создается проект и открывается в редакторе исходного файла.

## <a name="create-the-code"></a>Создание кода

Далее вы узнаете, как создать код для классического приложения Windows в Visual Studio.

### <a name="to-start-a-windows-desktop-application"></a>Запуск классического приложения Windows

1. Так же, как каждый C приложения и приложения C++ должны иметь `main` работать в качестве начальной точкой, каждый Windows классического приложения должен иметь `WinMain` функции. `WinMain` имеет следующий синтаксис:

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Сведения о параметры и возвращаемые значения этой функции см. в разделе [точка входа WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559).

   > [!NOTE]
   > Каковы этих дополнительных слов **обратного ВЫЗОВА**, или **HINSTANCE**, или  **\_в\_**? Традиционные API Windows использует определения типов и макросы препроцессора широко чтобы абстрагироваться часть сведений о типах и платформой кода, например соглашения о вызовах, **__declspec** объявления и прагма-директивы компилятора. В Visual Studio можно использовать IntelliSense [краткие сведения](/visualstudio/ide/using-intellisense#quick-info) возможность, чтобы узнать эти определения типов и макросов определения. Наведите курсор мыши на слово интерес, или выберите его и нажмите клавиши ctrl-K, ctrl-I — небольшого всплывающего окна, содержащего определение. Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense). Параметры и возвращаемые типы часто используют *заметки SAL* помогут catch ошибки программирования. Дополнительные сведения см. в разделе [использование аннотаций SAL для сокращения количества дефектов в коде C/C++](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Программы для настольных систем Windows требуется &lt;windows.h >. &lt;в файле Tchar.h > определяет `TCHAR` макрос, который разрешается в конечном счете для `wchar_t` Если символ ЮНИКОДА определен в проекте, в противном случае он разрешается в `char`.  При создании всегда с включенной поддержкой ЮНИКОДА, нет необходимости TCHAR, а затем можно просто использовать wchar_t напрямую.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Наряду с функцией `WinMain` в каждом классическом приложении Windows также должна быть определена функция оконной процедуры. Эта функция обычно называется `WndProc` , но ее можно назвать угодно. `WndProc` имеет следующий синтаксис:

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   В этой функции можно разрабатывать код для обработки *сообщений* , приложение получает из Windows при *события* возникать. Например, если пользователь нажмет кнопку "ОК" в приложении, Windows будет отправлять сообщения для вас и можно написать код внутри вашей `WndProc` функцию, которая не подходит, независимо от работы. Это называется *обработки* события. Можно обрабатывать только события, которые являются значимыми для приложения.

   Дополнительные сведения см. в разделе [процедуры окна](https://msdn.microsoft.com/library/windows/desktop/ms632593).

### <a name="to-add-functionality-to-the-winmain-function"></a>Добавление функциональных возможностей в функцию WinMain

1. В `WinMain` функции, необходимо заполнить структуру типа [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577). Эта структура содержит сведения о диалоговом окне, например, значок приложения, цвет фона окна, имя, отображаемое в заголовке окна и что очень важно, указатель на функцию в процедуру окна. В приведенном ниже примере показана типичная структура `WNDCLASSEX` .

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   Сведения о полях этой структуры см. в разделе [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577).

1. Необходимо зарегистрировать `WNDCLASSEX` с Windows, так что он знает об окне и отправку сообщений. Используйте [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587) функцией и передайте структуру класса окна в качестве аргумента. `_T` Макрос используется, так как мы используем `TCHAR` типа.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. Теперь можно создать окно. Используйте [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) функции.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   Эта функция возвращает `HWND`, являющийся дескриптором окна. Дескриптор похожа указатель, который используется для отслеживания открытых окон Windows. Дополнительные сведения см. в разделе [типы данных Windows](https://msdn.microsoft.com/library/windows/desktop/aa383751).

1. На этом этапе создания окна, но мы по-прежнему должны сообщить Windows, чтобы сделать его видимым. Это означает, что этот код делает следующее:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Отображается окно не имеет большое количество содержимого, поскольку еще не реализован `WndProc` функции. Другими словами приложение не еще обрабатывает сообщения, которые Windows теперь отправляет его.

1. Для обработки сообщений, мы добавьте цикл обработки сообщений должен прослушивать сообщения, отправляемые Windows. Когда приложение получает сообщение, этот цикл пересылает его вашей `WndProc` функции для обработки. Цикл обработки сообщений напоминает приведенный ниже код.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Дополнительные сведения о структурах и функциях в цикле обработки сообщений см. в разделе [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955), и [DispatchMessage ](https://msdn.microsoft.com/library/windows/desktop/ms644934).

   На этом этапе функция `WinMain` должна напоминать приведенный ниже код.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>Добавление функциональных возможностей в функцию WndProc

1. Чтобы включить обработку получаемых приложением сообщений функцией `WndProc` , реализуйте оператор switch.

   Одно важное сообщение для обработки является [WM_PAINT](https://msdn.microsoft.com/library/windows/desktop/dd145213) сообщения. Приложение получает это сообщение, когда часть его отображаемого окна требует обновления. Это событие может возникать, когда пользователь перемещает окно перед окна, а затем снова перемещает ее сейчас. Приложение не знает, при возникновении событий следующим образом; только Windows знает, поэтому она выводит уведомление с `WM_PAINT`. При первом отображении окна, все они должны обновляться.

   Для обработки `WM_PAINT` сообщений, первый вызов [BeginPaint](https://msdn.microsoft.com/library/windows/desktop/dd183362), далее обработайте логику расположения текста, кнопок и других элементов управления в окне, а затем вызвать [EndPaint](https://msdn.microsoft.com/library/windows/desktop/dd162598). В этом приложении логика между начальным и конечным вызовами является отображение строку «Hello, рабочий стол Windows!» "Hello, World!". В следующем коде Обратите внимание, что [TextOut](https://msdn.microsoft.com/library/windows/desktop/dd145133) функция используется для отображения строки.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC`в этом коде — это дескриптор контекста устройства — это структура данных, используемый Windows для позволяют приложению взаимодействовать с графической подсистемы. `BeginPaint` И `EndPaint` функции убедитесь, что приложение ведет себя как хорошо угла и не использует контекст устройства для больше, чем требуется для. Это гарантирует, что графическая подсистема доступна для использования другими приложениями.

1. Обычно приложение обрабатывает много других сообщений, например, [WM_CREATE](https://msdn.microsoft.com/library/windows/desktop/ms632619) при создании окна и [WM_DESTROY](https://msdn.microsoft.com/library/windows/desktop/ms632620) при закрытии окна. В приведенном ниже коде содержится базовое представление полной функции `WndProc` .

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>Создание кода

Как Ожидаемая, ниже приведен полный код в работающем приложении.

### <a name="to-build-this-example"></a>Сборка примера

1. Удалите все введенные вами в HelloWindowsDesktop.cpp в редакторе кода. Скопируйте этот код примера и вставьте его в HelloWindowsDesktop.cpp:

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. В меню **Построение** выберите **Построить решение**. Результаты компиляции появится в **выходной** в Visual Studio.

   ![Выполните построение проекта DesktopApp](../build/media/desktop-app-project-build-150.gif "построения проекта DesktopApp")

1. Чтобы запустить приложение, нажмите клавишу **F5**. Окно, содержащее текст «Hello, рабочий стол Windows!» должно отображаться в левом верхнем углу экрана.

   ![Запустите проект DesktopApp](../build/media/desktop-app-project-run-150.gif "запуска проекта DesktopApp")

Поздравляем! После изучения этого пошагового руководства и построение традиционных приложений для настольных компьютеров Windows.

## <a name="see-also"></a>См. также

[Классические приложения Windows](../windows/windows-desktop-applications-cpp.md)
