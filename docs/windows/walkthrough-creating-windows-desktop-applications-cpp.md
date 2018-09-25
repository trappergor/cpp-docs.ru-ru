---
title: 'Пошаговое руководство: Создание традиционного приложения рабочего стола Windows (C++) | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 09/18/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e9541517852696073a3dbbff560bb6c44fd3264
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029675"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Пошаговое руководство: Создание традиционного приложения рабочего стола Windows (C++)

В этом пошаговом руководстве показано, как создать традиционное классическое приложение Windows в Visual Studio. Вы создадите пример приложения использует Windows API для отображение «Hello, рабочий стол Windows!» "Hello, World!". Код, созданный в этом пошаговом руководстве, можно использовать в качестве шаблона для создания других классических приложений Windows.

API Windows (также называется Win32 API, Windows Desktop API и Windows Classic API) — это платформа на основе языка C для создания приложений Windows. Он еще в 1980-е и использовался для создания приложений Windows в течение десятилетий. Более сложных и проще для программы платформы построенных на базе этого API, например платформ .NET, ATL и MFC. Даже самые современные код для приложения универсальной платформы Windows и Store написаны на C + +/ WinRT использует этот API под. Дополнительные сведения о Windows API, см. в разделе [индекс API Windows](/windows/desktop/apiindex/windows-api-list). Существует много способов создания приложений Windows, но это был первым.

> [!IMPORTANT]
> Для краткости некоторые операторы кода, опущены в тексте. [Сборки кода](#build-the-code) в конце этого документа показан полный код.

## <a name="prerequisites"></a>Предварительные требования

- Компьютер под управлением Microsoft Windows 7 или более поздних версий. Мы рекомендуем использовать Windows 10 для обеспечения оптимальной среды разработки.

- Копия Visual Studio 2017. Сведения о том, как загрузить и установить Visual Studio, см. в разделе [установка Visual Studio](/visualstudio/install/install-visual-studio). Когда вы запускаете программу установки, убедитесь, что **разработка классических приложений C++** проверяется рабочей нагрузки. Не беспокойтесь, если эта рабочая нагрузка не были установлены при установке Visual Studio. Можно снова запустите установщик и установить его.

   ![Разработка классических приложений C++](../build/media/desktop-development-with-cpp.png "разработка классических приложений C++")

- Понимание основ использования интегрированной среде разработки Visual Studio. При использовании классических приложений Windows, прежде чем вы, вероятно, справляется. Общие сведения см. в разделе [Обзор возможностей интегрированной среды разработки Visual Studio](/visualstudio/ide/visual-studio-ide).

- Понимание достаточно основ языка C++ для выполнения этой процедуры. Не беспокойтесь, мы не слишком сложным.

## <a name="create-a-windows-desktop-project"></a>Создание проекта рабочего стола Windows

Выполните следующие действия для создания вашего первого проекта рабочего стола Windows и введите код для рабочее приложение рабочего стола Windows. Если вы используете версию Visual Studio, старше, чем Visual Studio 2017 версии 15.3, перейти к шагу [для создания проекта рабочего стола Windows в Visual Studio 2017 RTM](#create-in-vs2017-rtm).

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Создание проекта рабочего стола Windows в Visual Studio 2017 с обновлением 15.3 и более поздних версий

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В **новый проект** диалоговое окно, в области слева разверните **установленные** > **Visual C++**, а затем выберите **Windows Desktop**. В средней области выберите **мастер создания классических приложений Windows**.

   В **имя** введите имя проекта, например, *DesktopApp*. Нажмите кнопку **ОК**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-153.png "DesktopApp проекту имя")

1. В **проект приложения Windows** диалогового окна в разделе **тип приложения**выберите **Windows приложение (.exe)**. В поле **Дополнительные параметры**выберите **Пустой проект**. Выберите **ОК** для создания проекта.

   ![Создать в мастере проекта для настольных систем Windows DesktopApp](../build/media/desktop-app-new-project-wizard-153.png "Создание DesktopApp в мастере проекта для настольных систем Windows")

1. В **обозревателе решений**, щелкните правой кнопкой мыши **DesktopApp** проекта, выберите **добавить**, а затем выберите **новый элемент**.

   ![Добавить новый элемент к проекту DesktopApp](../build/media/desktop-app-project-add-new-item-153.gif "добавить новый элемент к проекту DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В **имя** введите имя файла, например, *HelloWindowsDesktop.cpp*. Выберите **Добавить**.

   ![Добавить CPP-файл к проекту DesktopApp](../build/media/desktop-app-add-cpp-file-153.png "добавить CPP-файл к проекту DesktopApp")

Теперь создания проекта и исходный файл открывается в редакторе. Чтобы продолжить, сразу перейти к [создания кода](#create-the-code).

### <a id="create-in-vs2017-rtm"></a> Чтобы создать проект для настольной системы Windows в Visual Studio 2017 RTM

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В **новый проект** диалоговое окно, в области слева разверните **установленные** > **шаблоны** > **Visual C++**, а затем выберите **Win32**. В средней области выберите шаблон **Проект Win32**.

   В **имя** введите имя проекта, например, *DesktopApp*. Нажмите кнопку **ОК**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-150.png "DesktopApp проекту имя")

1. На **Обзор** странице **мастер приложений Win32**, выберите **Далее**.

   ![Создание DesktopApp в общие сведения о мастере приложений Win32](../build/media/desktop-app-win32-wizard-overview-150.png "Создание DesktopApp в общие сведения о мастере приложений Win32")

1. На **параметры приложения** раздела **тип приложения**выберите **приложения Windows**. В поле **Дополнительные параметры**выберите **Пустой проект**. Выберите **Готово** для создания проекта.

   ![Создание DesktopApp в параметры мастера приложений Win32](../build/media/desktop-app-win32-wizard-settings-150.png "Создание DesktopApp в параметры мастера приложений Win32")

1. В **обозревателе решений**, щелкните правой кнопкой мыши проект DesktopApp, выберите **добавить**, а затем выберите **новый элемент**.

   ![Добавить новый элемент к проекту DesktopApp](../build/media/desktop-app-project-add-new-item-150.gif "добавить новый элемент к проекту DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В **имя** введите имя файла, например, *HelloWindowsDesktop.cpp*. Выберите **Добавить**.

   ![Добавить CPP-файл к проекту DesktopApp](../build/media/desktop-app-add-cpp-file-150.png "добавить CPP-файл к проекту DesktopApp")

Теперь создания проекта и исходный файл открывается в редакторе.

## <a name="create-the-code"></a>Создание кода

Далее вы узнаете, как создать код для классического приложения Windows в Visual Studio.

### <a name="to-start-a-windows-desktop-application"></a>Запуск классического приложения Windows

1. Так же, как каждый C приложения и приложения C++ должны иметь `main` функционировать в качестве отправной точки, каждый Windows, настольных приложений должен иметь `WinMain` функции. `WinMain` имеет следующий синтаксис:

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Сведения о параметрах и значениях, возвращаемых этой функцией, см. в разделе [точка входа WinMain](https://msdn.microsoft.com/library/windows/desktop/ms633559).

   > [!NOTE]
   > Что такое этих дополнительных слов, таких как `CALLBACK`, или `HINSTANCE`, или `_In_`? Традиционные API Windows использует определения типов и макросы препроцессора широко, чтобы абстрагироваться от конкретных некоторые из сведений о типах и платформой кодов, таких как соглашения о вызовах, **__declspec** объявления и директив pragma для компилятора. В Visual Studio можно использовать IntelliSense [краткие сведения](/visualstudio/ide/using-intellisense#quick-info) возможность, чтобы узнать, что определение этих определений typedef и макросы. Наведите указатель мыши над словом интерес, или выберите его и нажмите клавишу **Ctrl**+**K**, **Ctrl**+**я** для небольшое всплывающее окно с определением. Дополнительные сведения см. в статье [Using IntelliSense](/visualstudio/ide/using-intellisense) (Использование IntelliSense). Параметры и возвращаемые типы часто используют *примечания SAL* помогут вам catch ошибок программирования. Дополнительные сведения см. в разделе [использование аннотаций SAL для сокращения количества дефектов кода C/C++](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Программы для настольных систем Windows требуется &lt;windows.h >. &lt;в файле Tchar.h > определяет `TCHAR` макрос, который разрешается в конечном итоге к **wchar_t** Если символа ЮНИКОДА определен в проекте, в противном случае он разрешается в **char**.  Если всегда создаются с включенной поддержкой ЮНИКОДА, не нужны TCHAR и можно просто использовать его **wchar_t** напрямую.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Наряду с функцией `WinMain` в каждом классическом приложении Windows также должна быть определена функция оконной процедуры. Эта функция обычно называется `WndProc` , но вы можете назвать ее любым. `WndProc` имеет следующий синтаксис:

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   В этой функции можно написать код для обработки *сообщений* , приложение получает из Windows при *события* произойти. Например, если пользователь нажимает кнопку "ОК" в приложении, Windows отправит вам сообщение и вы можете написать код внутри вашей `WndProc` функцию, которая не подходит, независимо от работы. Это называется *обработка* событие. Можно обрабатывать только события, которые являются значимыми для приложения.

   Дополнительные сведения см. в разделе [процедуры окна](https://msdn.microsoft.com/library/windows/desktop/ms632593).

### <a name="to-add-functionality-to-the-winmain-function"></a>Добавление функциональных возможностей в функцию WinMain

1. В `WinMain` функции, заполнить структуру типа [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577). Эта структура содержит сведения об окне, например, значок приложения, цвет фона окна, имя, отображаемое в заголовке окна, а главное — указатель на функцию в процедуре окна. В приведенном ниже примере показана типичная структура `WNDCLASSEX` .

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

1. Необходимо зарегистрировать `WNDCLASSEX` с Windows, чтобы он знал о окна и как отправлять сообщения на него. Используйте [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587) функции и передайте структуру класса окна в качестве аргумента. `_T` Макрос используется, так как мы используем `TCHAR` типа.

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

1. Теперь можно создать окно. Используйте [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) функции.

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

   Эта функция возвращает `HWND`, являющийся дескриптором окна. Дескриптор является подобно указатель, который использует Windows для отслеживания открытых окон. Дополнительные сведения см. в разделе [типы данных Windows](/windows/desktop/WinProg/windows-data-types).

1. На этом этапе создания окна, но мы по-прежнему должны сообщить Windows, чтобы сделать его видимым. Вот что делает этот код:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Отображаемого окна не имеет большое количество содержимого, поскольку еще не реализован `WndProc` функции. Другими словами приложение не еще обрабатывает сообщения, которые Windows теперь может отправлять к нему.

1. Для обработки сообщений, мы сначала добавить цикл обработки сообщений для прослушивания сообщений, отправляемых в Windows. Когда приложение получает сообщение, этот цикл пересылает его к вашей `WndProc` функции для обработки. Цикл обработки сообщений напоминает приведенный ниже код.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Дополнительные сведения о структурах и функциях в цикл обработки сообщений, см. в разделе [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage), и [DispatchMessage ](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).

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

   Одно важное сообщение для обработки является [WM_PAINT](/windows/desktop/gdi/wm-paint) сообщения. Приложение получает это сообщение, когда часть его отображаемого окна требует обновления. Это событие может вызываться, когда пользователь перемещает окно перед окна, а затем снова перемещает ее сейчас. Приложение не знает, при возникновении событий следующим образом; только Windows знает, поэтому она выводит уведомление с `WM_PAINT`. При первом отображении окна его необходимо обновить.

   Для обработки `WM_PAINT` сообщений, первый вызов [BeginPaint](/windows/desktop/api/winuser/nf-winuser-beginpaint), затем обработайте логику расположения текста, кнопок и других элементов управления в окне, а затем вызовите [EndPaint](/windows/desktop/api/winuser/nf-winuser-endpaint). Это приложение логика между начальным и конечным вызовами предполагает отображение строки «Hello, рабочий стол Windows!» "Hello, World!". В приведенном ниже коде Обратите внимание, что [TextOut](/windows/desktop/api/wingdi/nf-wingdi-textouta) функция используется для отображения строки.

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

   `HDC` в этом коде является дескриптор контекста устройства, который представляет собой структуру данных, который использует Windows для включения взаимодействия с подсистемой графики. `BeginPaint` И `EndPaint` функции гарантируют, что приложение ведет себя как сознательный гражданин и не использует контекст устройства в течение более длительного времени, чем требуется. Это гарантирует, что графическая подсистема доступна для использования другими приложениями.

1. Обычно приложение обрабатывает много других сообщений, например, [WM_CREATE](/windows/desktop/winmsg/wm-create) при первоначальном создании окна и [WM_DESTROY](/windows/desktop/winmsg/wm-destroy) при закрытии окна. В приведенном ниже коде содержится базовое представление полной функции `WndProc` .

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

Как мы и говорили, ниже приведен полный код для работы приложения.

### <a name="to-build-this-example"></a>Сборка примера

1. Удалите весь код, который вы ввели в *HelloWindowsDesktop.cpp* в редакторе. Скопируйте этот код примера и вставьте его в *HelloWindowsDesktop.cpp*:

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

1. В меню **Построение** выберите **Построить решение**. Результаты компиляции появится в **вывода** окно в Visual Studio.

   ![Постройте проект DesktopApp](../build/media/desktop-app-project-build-150.gif "построения проекта DesktopApp")

1. Чтобы запустить приложение, нажмите клавишу **F5**. Окно, содержащее текст «Hello, рабочий стол Windows!» должно отображаться в левом верхнем углу экрана.

   ![Запустите проект DesktopApp](../build/media/desktop-app-project-run-157.png "запустить проект DesktopApp")

Поздравляем! Вы это пошаговое руководство успешно и создали традиционное классическое приложение Windows.

## <a name="see-also"></a>См. также

[Классические приложения Windows](../windows/windows-desktop-applications-cpp.md)