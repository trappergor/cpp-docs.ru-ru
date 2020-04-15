---
title: 'Пошаговая прогулка: Создайте традиционное приложение для рабочего стола Windows'
description: Как создать минимальное традиционное приложение Windows Desktop с помощью Visual Studio, C и API Win32
ms.custom: get-started-article
ms.date: 11/03/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: da74778e79a08dd3ed2b5be0675981425264bdc0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351840"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Пошаговая прогулка: Создайте традиционное приложение для рабочего стола Windows

В этом пошаговом показании, как создать традиционное настольное приложение Windows в Visual Studio. Пример приложения, которое вы создадите, использует API Windows для отображения "Hello, Windows desktop!" "Hello, World!". Код, созданный в этом пошаговом руководстве, можно использовать в качестве шаблона для создания других классических приложений Windows.

API Windows (также известный как Win32 API, Windows Desktop API и Windows Classic API) — это платформа на основе C-языков для создания приложений Windows. Он существует с 1980-х годов и используется для создания приложений Windows на протяжении десятилетий. Более продвинутые и простые в программировании платформы были построены поверх API Windows. Например, MFC, ATL, платформы .NET. Даже самый современный код Windows Runtime для приложений UWP и Store, написанный в си/Винрт, использует Под ним API Windows. Для получения дополнительной информации о [Windows API Index](/windows/win32/apiindex/windows-api-list)API Windows см. Существует множество способов создания приложений для Windows, но вышеуказанный процесс был первым.

> [!IMPORTANT]
> Для краткости некоторые кодовые заявления опущены в тексте. Раздел [«Сборка кода»](#build-the-code) в конце этого документа показывает полный код.

## <a name="prerequisites"></a>Предварительные требования

- Компьютер под управлением Microsoft Windows 7 или более поздних версий. Для обеспечения оптимальной среды разработки рекомендуется использовать Windows 10.

- Копия Visual Studio. Сведения о скачивании и установке Visual Studio см. в [этой статье](/visualstudio/install/install-visual-studio). Когда вы запускаете установщик, убедитесь, что установлена рабочая нагрузка **Разработка классических приложений на C++**. Не беспокойтесь, если вы не установили эту рабочую нагрузку при установке Visual Studio. Вы можете снова запустить установщик и установить ее сейчас.

   ![разработка классических приложений на C++;](../build/media/desktop-development-with-cpp.png "разработка классических приложений на C++;")

- Базовые значения об использовании интегрированной среды разработки Visual Studio. Если вы уже использовали классические приложения для Windows, вы, вероятно, справитесь. Общие сведения см. в [обзоре возможностей интегрированной среды разработки Visual Studio](/visualstudio/ide/visual-studio-ide).

- Основные навыки владения языком C++. Не волнуйтесь, мы не будем делать ничего сложного.

## <a name="create-a-windows-desktop-project"></a>Создание настольного проекта Windows

Выполните эти действия, чтобы создать свой первый настольный проект Windows. По мере того как вы идете, вы введете код для работая приложения настольного компьютера Windows. Чтобы просмотреть документацию для предпочтительной версии Visual Studio, используйте элемент управления селектора **версии.** Он находится в верхней части таблицы содержимого на этой странице.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Создание настольного проекта Windows в Visual Studio 2019

1. В главном меню выберите **Файл ** > **Создать ** > **Проект**, чтобы открыть диалоговое окно **Создание проекта**.

1. В верхней части диалога установите **Язык** на **СЗ,** установите **платформу** для **Windows**и установите **тип проекта** на **рабочий стол.**

1. Из отфильтрованного списка типов проектов выберите **Windows Desktop Wizard,** а затем выберите **Next.** На следующей странице введите название проекта, например, *DesktopApp*.

1. Нажмите кнопку **Создать**, чтобы создать проект.

1. Теперь отображается диалог **проекта Windows Desktop** Project. В **типе приложения**выберите **приложение Desktop (.exe).** В поле **Дополнительные параметры**выберите **Пустой проект**. Выберите **OK** для создания проекта.

1. В **Solution Explorer**, правой кнопкой мыши на **desktopApp** проекта, **выберите Добавить,** а затем выбрать **новый пункт**.

   ![Добавление нового элемента в проект DesktopApp](../build/media/desktop-app-project-add-new-item-153.gif "Добавление нового элемента в проект DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **Name** введите имя файла, например, *HelloWindowsDesktop.cpp.* Выберите **Добавить**.

   ![Добавление файла .cpp в проект DesktopApp](../build/media/desktop-app-add-cpp-file-153.png "Добавление файла .cpp в проект DesktopApp")

Ваш проект теперь создан и ваш исходный файл открыт в редакторе. Чтобы продолжить работу, пропустите вперед, чтобы [создать код.](#create-the-code)

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Создание настольного проекта Windows в Visual Studio 2017

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В диалоговом окне **нового проекта,** в левом стекле, расширьте **установленный** > **визуальный C '**, затем выберите Windows **Desktop.** В середине панели выберите **Windows Desktop Wizard.**

   В поле **Name** введите название проекта, например, *DesktopApp.* Выберите **OK**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-153.png "Назовите проект DesktopApp")

1. В диалоге **проекта Windows Desktop,** под **типом приложения,** выберите **приложение Windows (.exe).** В поле **Дополнительные параметры**выберите **Пустой проект**. Убедитесь, что **предварительно собранный заголовок** не выбран. Выберите **OK** для создания проекта.

1. В **Solution Explorer**, правой кнопкой мыши на **desktopApp** проекта, **выберите Добавить,** а затем выбрать **новый пункт**.

   ![Добавление нового элемента в проект DesktopApp](../build/media/desktop-app-project-add-new-item-153.gif "Добавление нового элемента в проект DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **Name** введите имя файла, например, *HelloWindowsDesktop.cpp.* Выберите **Добавить**.

   ![Добавление файла .cpp в проект DesktopApp](../build/media/desktop-app-add-cpp-file-153.png "Добавление файла .cpp в проект DesktopApp")

Ваш проект теперь создан и ваш исходный файл открыт в редакторе. Чтобы продолжить работу, пропустите вперед, чтобы [создать код.](#create-the-code)

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Создание настольного проекта Windows в Visual Studio 2015

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В диалоговом окне **нового проекта,** в левом стекле, расширьте **установленные** > **шаблоны** > **Visual C ,** а затем выберите **Win32**. В средней области выберите шаблон **Проект Win32**.

   В поле **Name** введите название проекта, например, *DesktopApp.* Выберите **OK**.

   ![Назовите проект DesktopApp](../build/media/desktop-app-new-project-name-150.png "Назовите проект DesktopApp")

1. На странице **Обзор** **Мастера Приложения Win32**выберите **следующий**.

   ![Создание DesktopApp в Обзоре Мастера приложений Win32](../build/media/desktop-app-win32-wizard-overview-150.png "Создание DesktopApp в Обзоре Мастера приложений Win32")

1. На странице **Настройки приложений,** под **типом приложения,** выберите **приложение Windows.** Под **дополнительными опциями,** отменить проверку **Предварительного заголовка,** а затем выберите **Пустой проект.** Выберите **finish** для создания проекта.

1. В **Solution Explorer**, правой кнопкой мыши на desktopApp проекта, **выберите Добавить,** а затем выбрать **новый пункт**.

   ![Добавление нового элемента в проект DesktopApp](../build/media/desktop-app-project-add-new-item-150.gif "Добавление нового элемента в проект DesktopApp")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **Name** введите имя файла, например, *HelloWindowsDesktop.cpp.* Выберите **Добавить**.

   ![Добавление файла .cpp в проект DesktopApp](../build/media/desktop-app-add-cpp-file-150.png "Добавление файла .cpp в проект DesktopApp")

Ваш проект теперь создан и ваш исходный файл открыт в редакторе.

::: moniker-end

## <a name="create-the-code"></a>Создание кода

Далее вы узнаете, как создать код для настольного приложения Windows в Visual Studio.

### <a name="to-start-a-windows-desktop-application"></a>Запуск классического приложения Windows

1. Точно так же, как каждое приложение `main` C и приложение СЗ должны иметь `WinMain` функцию в качестве отправной точки, каждое настольное приложение Windows должно иметь функцию. `WinMain` имеет следующий синтаксис:

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Для получения информации о параметрах и значении возврата этой функции, [см.](/windows/win32/api/winbase/nf-winbase-winmain)

   > [!NOTE]
   > Что все эти дополнительные `CALLBACK`слова, `HINSTANCE`такие `_In_`как , или , или? Традиционный Windows API широко использует типографы и препроцессорные макросы, чтобы абстрагировать некоторые детали типов и кода, специфичные для платформы, такие как вызовные конвенции, **__declspec** декларации и прагмы компилятора. В Visual Studio вы можете использовать функцию IntelliSense [Быстрая информация,](/visualstudio/ide/using-intellisense#quick-info) чтобы увидеть, что эти typedefs и макросы определить. Нависните мышь над словом интереса, или выберите его и нажмите **Ctrl**+**K**, **Ctrl**+**I** для небольшого всплывающее окно, которое содержит определение. Дополнительные сведения см. в разделе [Using IntelliSense](/visualstudio/ide/using-intellisense). Параметры и типы возврата часто используют *SAL Аннотации,* чтобы помочь вам улавливать ошибки программирования. Для получения дополнительной информации [см.](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)

1. Настольные &lt;программы Windows требуют> windows.h. &lt;tchar.h> определяет `TCHAR` макрос, который решает в конечном счете, чтобы **wchar_t,** если символ UNICODE определен в вашем проекте, в противном случае он решает свести на **себя.**  Если вы всегда строите с включенным UNICODE, вам не нужно TCHAR и можете просто использовать **wchar_t** напрямую.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Наряду `WinMain` с функцией каждое настольное приложение Windows должно также иметь функцию оконной процедуры. Эта функция, `WndProc`как правило, называется, но вы можете назвать его все, что вам нравится. `WndProc` имеет следующий синтаксис:

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   В этой функции вы пишете код для обработки *сообщений,* которые приложение получает от Windows во время *событий.* Например, если пользователь выбирает кнопку OK в вашем приложении, Windows отправит вам `WndProc` сообщение, и вы можете написать код внутри вашей функции, который делает любую работу, соответствующую. Это называется *обработка* события. Вы обрабатываете только события, имеющие отношение к вашему приложению.

   Дополнительные сведения см. в разделе [Процедуры окна](/windows/win32/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>Добавление функциональных возможностей в функцию WinMain

1. В `WinMain` функции заполняют структуру типа [WNDCLASSEX.](/windows/win32/api/winuser/ns-winuser-wndclassexw) Структура содержит информацию о окне: значок приложения, цвет фона окна, имя для отображения в заголовке бара, среди прочего. Важно отметить, что он содержит функцию указателя на процедуру окна. В приведенном ниже примере показана типичная структура `WNDCLASSEX` .

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

   Для получения информации о полях структуры выше, [см.](/windows/win32/api/winuser/ns-winuser-wndclassexw)

1. Зарегистрируйте `WNDCLASSEX` windows, чтобы она узнает о вашем окне и о том, как отправлять ему сообщения. Воспользуйтесь функцией [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) и передайте структуру класса окна в качестве аргумента. Макрос `_T` используется, потому `TCHAR` что мы используем тип.

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

1. Теперь можно создать окно. Воспользуйтесь функцией [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) .

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

   Эта функция `HWND`возвращает, который является ручкой к окну. Ручка чем-то похожа на указатель, который Windows использует для отслеживания открытых окон. Дополнительные сведения см. в разделе [Типы данных Windows](/windows/win32/WinProg/windows-data-types).

1. На этом этапе окно создано, но нам все еще нужно сказать Windows, чтобы сделать его видимым. Вот что делает этот код:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Отображеное окно не имеет большого содержимого, потому что вы еще не реализовали функцию. `WndProc` Другими словами, приложение еще не обрабатывает сообщения, которые Windows теперь отправляет ему.

1. Для обработки сообщений мы сначала добавляем цикл сообщений для прослушивания сообщений, отправляемых Windows. Когда приложение получает сообщение, этот цикл отправляет `WndProc` его в вашу функцию для обработки. Цикл обработки сообщений напоминает приведенный ниже код.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Дополнительные сведения о структурах и функциях, используемых в цикле обработки сообщений, см. в разделах, посвященных [MSG](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).

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

   Одним из важных сообщений для обработки является [сообщение WM_PAINT.](/windows/win32/gdi/wm-paint) Приложение получает `WM_PAINT` сообщение, когда часть отображаемого окна должна быть обновлена. Событие может произойти, когда пользователь перемещает окно перед окном, а затем перемещает его снова. Приложение не знает, когда происходят эти события. Только Windows знает, поэтому она уведомляет ваше приложение с сообщением. `WM_PAINT` Когда окно сначала отображается, все это должно быть обновлено.

   Для обработки сообщения `WM_PAINT` сначала вызовите метод [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint), далее обработайте логику расположения текста, кнопок и других элементов управления в окне, а затем вызовите метод [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint). Для приложения логика между началом вызова и окончанием вызова заключается в отображении строки "Здравствуйте, рабочий стол Windows!" "Hello, World!". В приведенном ниже коде обратите внимание, что функция [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) используется для отображения строки.

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

   `HDC`в коде находится ручка к контексту устройства, которая представляет собой структуру данных, которую Windows использует для того, чтобы ваше приложение могли общаться с графической подсистемой. `BeginPaint` Функции `EndPaint` и функции делают ваше приложение похожим на хорошего гражданина и не использует контекст устройства дольше, чем это необходимо. Функции помогают сделать графическую подсистему доступной для использования другими приложениями.

1. Обычно приложение обрабатывает многие другие сообщения. Например, [WM_CREATE,](/windows/win32/winmsg/wm-create) когда окно сначала создается, и [WM_DESTROY,](/windows/win32/winmsg/wm-destroy) когда окно закрыто. В приведенном ниже коде содержится базовое представление полной функции `WndProc` .

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

## <a name="build-the-code"></a>Сборка кода

Как и было обещано, вот полный код для рабочего приложения.

### <a name="to-build-this-example"></a>Сборка примера

1. Удалите любой код, который вы ввели в *HelloWindowsDesktop.cpp* в редакторе. Скопируйте этот пример кода, а затем вставьте его в *HelloWindowsDesktop.cpp:*

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
      _In_opt_ HINSTANCE hPrevInstance,
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

1. В меню **Построение** выберите **Построить решение**. Результаты компиляции должны отображаться в окне **вывода** в Visual Studio.

   ![Создайте проект DesktopApp](../build/media/desktop-app-project-build-150.gif "Создайте проект DesktopApp")

1. Чтобы запустить приложение, нажмите клавишу **F5**. Окно, содержащее текст "Здравствуйте, рабочий стол Windows!" должно отображаться в левом верхнем углу экрана.

   ![Выполнить проект DesktopApp](../build/media/desktop-app-project-run-157.PNG "Выполнить проект DesktopApp")

Поздравляем! Вы завершили это пошаговое походе и создали традиционное настольное приложение Windows.

## <a name="see-also"></a>См. также раздел

[Классические приложения Windows](../windows/windows-desktop-applications-cpp.md)
