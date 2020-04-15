---
title: Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
ms.openlocfilehash: 72501ba32d3b8b9a5c5fd8dd0c56f0628642b147
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374459"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI

Следующие шаги показывают, как создать пользовательский контроль .NET Framework, автор управления пользователем в библиотеке класса управления (в частности, проект библиотеки управления Windows), а затем скомпилировать проект в сборку. Контроль можно использовать из приложения MFC, которое использует классы, полученные из [класса CView](../mfc/reference/cview-class.md) и [CWinFormsView Class.](../mfc/reference/cwinformsview-class.md)

Для получения информации о том, как создать управление пользователем Windows Forms и создать [библиотеку](/dotnet/framework/winforms/controls/how-to-author-composite-controls)класса управления, см.

> [!NOTE]
> В некоторых случаях элементы управления Windows Forms, такие как управление сеткой сторонних сетей, могут вести себя ненадежно при размещении в приложении MFC. Рекомендуемое решение заключается в том, чтобы поместить управление пользователем форм Windows в приложение MFC и поместить сторонний элемент управления сеткой внутри управления пользователем.

Эта процедура предполагает, что вы создали проект библиотеки управления Windows Forms Library под названием WindowsFormsControlLibrary1, в рамках процедуры [Как: Создать управление пользователем и хостом в Dialog Box.](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

### <a name="to-create-the-mfc-host-application"></a>Создание приложения мСТ

1. Создайте проект приложения MFC.

   В меню **файла** выберите **Новый**, а затем нажмите **Project**. В папке **Visual C'** выберите **приложение MFC**.

   В поле **Name** `MFC02` введите и измените настройку **решения** для **добавления в решение.** Нажмите кнопку **ОК**.

   В **MFC Приложение Мастера**, принять все по умолчанию, а затем нажмите **Закончить**. Это создает приложение MFC с интерфейсом multiple Document.

1. Нанастройка проекта для поддержки общего языкового runtime (CLR).

   В **Solution Explorer**щелкните по узлам `MFC01` проекта и выберите **свойства** из контекстного меню. Отображается диалоговая коробка **Страниц свойств.**

   Под **свойствами конфигурации**выберите **Общий**. В разделе **«По умолчанию» проекта «По умолчанию»** установите **поддержку общего времени выполнения языка** для **поддержки общего времени выполнения языка (/clr).**

   Под **свойствами конфигурации**расширьте **C/C и** щелкните **общий** узл. Установите **информационный формат Debug** для **базы данных программ (/Ци).**

   Нажмите на узла **генерации кода.** Установить **Включить Минимальная Перестроить** **до No (/Gm-)**. Также установите **основные проверки времени выполнения** **по умолчанию.**

   Нажмите **OK,** чтобы применить изменения.

1. В *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее), добавьте следующую строку:

    ```
    #using <System.Windows.Forms.dll>
    ```

1. Добавьте ссылку на элемент управления .NET.

   В **Solution Explorer**, `MFC02` правой кнопкой мыши узла проекта и выберите **Добавить**, **Ссылки**. На **странице свойств**нажмите **Добавить новую ссылку,** выберите WindowsFormsControlLibrary1 (под вкладкой **Проекты)** и нажмите **OK**. Это добавляет ссылку в виде опции компилятора [/FU,](../build/reference/fu-name-forced-hash-using-file.md) так что программа будет компилировать; он также копирует WindowsFormsControlLibrary1.dll в каталог `MFC02` проекта, так что программа будет работать.

1. В stdafx.h, найти эту строку:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Добавьте следующие строки над ним:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Измените класс представления таким образом, чтобы он унаследовал его от [CWinFormsView](../mfc/reference/cwinformsview-class.md).

   В MFC02View.h замените [CView](../mfc/reference/cview-class.md) [cWinFormsView](../mfc/reference/cwinformsview-class.md) так, чтобы код отосвазан следующим образом:

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   Если вы хотите добавить дополнительные представления в приложение MDI, вам нужно будет позвонить [в CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) для каждого создаваемого представления.

1. Измените файл MFC02View.cpp, чтобы изменить CView на CWinFormsView на IMPLEMENT_DYNCREATE макро- и карта сообщений и заменить существующий пустой конструктор с конструктором, показанным ниже:

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. Постройте и запустите проект.

   В **Solution Explorer**, правой кнопкой мыши MFC02 и выберите Набор в качестве **startUp проекта.**

   В меню **Сборка** выберите **Построить решение**.

   В меню **Debug** нажмите **«Старт» без отладки.**

## <a name="see-also"></a>См. также раздел

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
