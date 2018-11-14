---
title: Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
ms.openlocfilehash: f6b7b7b3d1cb5ed9f3cd2b3655b45aaac8d8d195
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524928"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC

MFC представлен класс шаблона [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) таким образом, чтобы можно было разместить пользовательский элемент управления Windows Forms (<xref:System.Windows.Forms.UserControl>) в модальное или немодальное диалоговое окно MFC. `CWinFormsDialog` является производным от класса библиотеки MFC [CDialog](../mfc/reference/cdialog-class.md), поэтому можно запустить в модальном или немодальном диалоговом окне.

Процесс, `CWinFormsDialog` используется пользовательский элемент управления, аналогична описанной в [размещение элемента управления формы пользователя Windows в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). Тем не менее `CWinFormsDialog` управляет инициализацией и размещением пользовательского элемента управления, таким образом, чтобы не нужно быть запрограммированы вручную.

Образец приложения, Windows Forms с MFC, см. в разделе [MFC и Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC

1. Создайте проект приложения MFC.

   На **файл** меню, выберите **New**, а затем нажмите кнопку **проекта**. В **Visual C++** папку, выберите **приложения MFC**.

   В **имя** введите `MFC03` и измените параметр решение для **добавить решение**. Нажмите кнопку **ОК**.

   В **мастер приложений MFC**, примите все значения по умолчанию и нажмите кнопку **Готово**. Это создает приложение MFC с интерфейсом MDI.

1. Настройка проекта.

   В **обозревателе решений**, щелкните правой кнопкой мыши **MFC03** узел проекта и выберите **свойства**. **Страницы свойств** откроется диалоговое окно.

   В **страницы свойств** отображаемое в диалоговом окне **свойства конфигурации** дерева, выберите **Общие**, а затем в **проекта по умолчанию**задайте **поддержки Common Language Runtime** для **поддержка среды CLR (/ clr)**. Нажмите кнопку **ОК**.

1. Добавьте ссылку на элемент управления .NET.

   В **обозревателе решений**, щелкните правой кнопкой мыши **MFC03** узел проекта и выберите **добавить**, **ссылки**. В **страницу свойств**, нажмите кнопку **добавить новую ссылку**, выберите проект WindowsControlLibrary1 (в разделе **проекты** вкладку) и нажмите кнопку **ОК**. Это действие добавляет ссылку в виде [/FU](../build/reference/fu-name-forced-hash-using-file.md) компилятора параметр, чтобы программа будет скомпилирована; он также копирует WindowsControlLibrary1.dll в `MFC03` каталог проекта, что программа будет выполняться.

1. Добавить `#include <afxwinforms.h>` файл stdafx.h, в конце существующего `#include` инструкций.

1. Добавьте новый класс, который наследуется от класса `CDialog`.

   Щелкните правой кнопкой имя проекта и Добавление класса MFC (именем CHostForWinForm), который наследуется от класса `CDialog`. Так как ресурс диалогового окна не требуется, можно удалить идентификатор ресурса (выберите **представление ресурсов**, разверните **диалоговое окно** папку и удалить `IDD_HOSTFORWINFORM` ресурсов.  Удалите все ссылки на идентификатор в коде.).

1. Замените `CDialog` в файлах CHostForWinForm.h и CHostForWinForm.cpp классом с `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.

1. Вызовите метод DoModal для класса CHostForWinForm.

   В файл MFC03.cpp добавьте `#include "HostForWinForm.h"`.

   Перед оператором return в определении CMFC03App::InitInstance добавьте следующую команду:

    ```cpp
    CHostForWinForm m_HostForWinForm;
    m_HostForWinForm.DoModal();
    ```

1. Постройте и запустите проект.

   В меню **Сборка** выберите **Собрать решение**.

   На **Отладка** меню, щелкните **Запуск без отладки**.

   Далее добавим код для отслеживания состояния элемента управления в формах Windows Forms из приложения MFC.

1. Добавьте обработчик для OnInitDialog.

   Отображение **свойства** окно (F4). В **представление классов**, выберите класс CHostForWinForm. В **свойства** мыши выберите переопределяет и в строке OnInitDialog щелкните левый столбец и выберите пункт \< Добавить >. Это добавляет следующую строку в файл CHostForWinForm.h:

    ```cpp
    virtual BOOL OnInitDialog();
    ```

1. Определите обработчик событий OnInitDialog (в файле CHostForWinForm.cpp) следующим образом:

    ```cpp
    BOOL CHostForWinForm::OnInitDialog() {
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);
       return TRUE;
    }
    ```

1. Далее добавьте обработчик событий OnButton1. Добавьте следующие строки в раздел public класса CHostForWinForm в файле CHostForWinForm.h:

    ```cpp
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );

    BEGIN_DELEGATE_MAP( CHostForWinForm )
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );
    END_DELEGATE_MAP()
    ```

   В файле CHostForWinForm.cpp добавьте следующее определение:

    ```cpp
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )
    {
       System::Windows::Forms::MessageBox::Show("test");
    }
    ```

1. Постройте и запустите проект. При нажатии кнопки, которая находится в форме Windows, будет выполняться код в приложении MFC.

    Далее добавим код для отображения кода MFC значение в текстовом поле в форме Windows.

1. В разделе открытого класса CHostForWinForm в файле CHostForWinForm.h добавьте следующее объявление:

    ```cpp
    CString m_sEditBoxOnWinForm;
    ```

1. В определении DoDataExchange в файле CHostForWinForm.cpp добавьте следующие три строки в конец функции:

    ```cpp
    if (pDX->m_bSaveAndValidate)
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);
    else
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);
    ```

1. В определении событий OnButton1 в файле CHostForWinForm.cpp добавьте следующие три строки в конец функции:

    ```cpp
    this->UpdateData(TRUE);
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);
    System::Windows::Forms::MessageBox::Show(z);
    ```

1. Постройте и запустите проект.

## <a name="see-also"></a>См. также

<xref:System.Windows.Forms.UserControl?displayProperty=fullName>
[Использование пользовательского элемента управления формы Windows в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)