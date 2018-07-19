---
title: 'Как: Создание пользовательского элемента управления и узла Просмотр MDI | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 449f0026cd2d7603ceb190cc747138189313974f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136487"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Практическое руководство. Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI
Ниже показано, как создать пользовательский элемент управления .NET Framework, создать пользовательский элемент управления в библиотеке классов (в частности, в проекте библиотеки элементов управления Windows) и затем скомпилировать проект в сборку. Элемент управления может быть обработано из приложения MFC, который использует классы, производные от [CView Class](../mfc/reference/cview-class.md) и [CWinFormsView класс](../mfc/reference/cwinformsview-class.md).  
  
 Сведения о том, как создать пользовательский элемент управления Windows Forms и создания библиотеки классов элементов управления см. в разделе [как: автор пользовательские элементы управления](/dotnet/framework/winforms/controls/how-to-author-composite-controls).  
  
> [!NOTE]
>  В некоторых случаях элементы управления Windows Forms, такие как элемент управления DataGrid сторонних разработчиков, работают не стабильно при размещении в приложении MFC. Рекомендуется разместить пользовательский элемент управления формы Windows Forms в приложении MFC и поместите элемент управления DataGrid сторонних внутри пользовательского элемента управления.  
  
 Предполагается, что вы создали проект библиотеки элементов управления Windows Forms, с именем WindowsFormsControlLibrary1, согласно процедуру, описанную в [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Создайте проект приложения MFC.  
  
     На **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**. В **Visual C++** выберите **приложение MFC**.  
  
     В **имя** введите `MFC02` и измените **решения** параметру **добавить решение**. Нажмите кнопку **ОК**.  
  
     В **мастер приложений MFC**, примите параметры по умолчанию и нажмите кнопку **Готово**. Это создает приложение MFC с интерфейсом MDI.  
  
2.  Настройка проекта для поддержки Common Language Runtime (CLR).  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши `MFC01` узел проекта и выберите **свойства** в контекстном меню. **Страницы свойств** откроется диалоговое окно.  
  
     В разделе **свойства конфигурации**выберите **Общие**. В разделе **проекта по умолчанию** установите **поддержки Common Language Runtime** для **поддержка среды CLR (/ clr)**.  
  
     В разделе **свойства конфигурации**, разверните **C/C++** и нажмите кнопку **Общие** узла. Задать **формат отладочной информации** для **(/Zi) база данных программы**.  
  
     Нажмите кнопку **создания кода** узла. Задать **включить минимальное перестроение** для **нет (/ Gm-)**. Кроме того, задать **основные проверки времени выполнения** для **по умолчанию**.  
  
     Нажмите кнопку **ОК** для применения изменений.  
  
3.  В файле stdafx.h добавьте следующую строку:  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  Добавьте ссылку на элемент управления .NET.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши `MFC02` узел проекта и выберите **добавить**, **ссылки**. В **страницу свойств**, нажмите кнопку **добавить новую ссылку**, выберите WindowsFormsControlLibrary1 (под **проекты** вкладку) и нажмите кнопку **ОК** . Добавлена ссылка в виде [/FU](../build/reference/fu-name-forced-hash-using-file.md) компилятора параметр, чтобы программа будет компилироваться; также он копирует WindowsFormsControlLibrary1.dll в `MFC02` проект каталогов, чтобы программа будет запущена.  
  
5.  В файле stdafx.h найдите следующую строку:  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Добавьте эти строки над ним.  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Измените класс представления так, чтобы он наследовал [CWinFormsView](../mfc/reference/cwinformsview-class.md).  
  
     В файле MFC02View.h, замените [CView](../mfc/reference/cview-class.md) с [CWinFormsView](../mfc/reference/cwinformsview-class.md) , чтобы код имеет следующий вид:  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     Если нужно добавить дополнительное представление в приложение MDI, необходимо вызвать [CWinApp::AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) для каждого представления, которые вы создаете.  
  
7.  Измените файл MFC02View.cpp, чтобы сделать CWinFormsView CView в implement_dyncreate-макрос и сопоставление сообщений и замените имеющийся пустой конструктор с помощью конструктора, показано ниже:  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  Постройте и запустите проект.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши MFC02 и выберите **Назначить запускаемым проектом**.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, нажмите кнопку **Запуск без отладки**.  
  
## <a name="see-also"></a>См. также  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)