---
title: Практическое руководство. Привязка данных DDX-DDV к элементам управления Windows Forms
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: 31629a4db2559112ba49f5c069b08de7abdfc2db
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754347"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) вызывает [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) для создания элемента управления, соответствующий идентификатору управления ресурсами. Если вы `DDX_ManagedControl` используете `CWinFormsControl` для управления (в коде, `CreateManagedControl` генерируемом мастером), не следует звонить явно для того же элемента управления.

Позвоните `DDX_ManagedControl` в [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) для создания элементов управления из итогов ресурсов. Для обмена данными не требуется использовать функции DDX/DDV с элементами управления Windows Forms. Вместо этого можно разместить код для доступа к `DoDataExchange` свойствам управляемого управления в методе вашего типа диалогов (или представления), как в следующем примере.

Ниже приводится следующий пример, как связать родную строку C's с управлением пользователя .NET.

## <a name="example"></a>Пример

Ниже приводится пример связывания данных DDX/DDV строки `m_str` `NameText` MFC с пользовательским свойством управления пользователем .NET.

Элемент управления создается, когда [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызывает `CMyDlg::DoDataExchange` в первый `m_UserControl` раз, `DDX_ManagedControl` так что любой код, который ссылки должны прийти после вызова.

Этот код можно реализовать в созданном приложением MFC01 [Как: создать управление пользователем и хостов в dialog Box.](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

Поместите следующий код в декларацию CMFC01Dlg:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>Пример

Поместите следующий код в реализацию CMFC01Dlg:

```cpp
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)
{
   CDialog::DoDataExchange(pDX);
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);

   if (pDX->m_bSaveAndValidate) {
      m_str = m_MyControl->textBox1->Text;
   } else
   {
      m_MyControl->textBox1->Text = gcnew System::String(m_str);
   }
}
```

## <a name="example"></a>Пример

Теперь мы добавим метод обработчика для нажатия на кнопку OK. Нажмите на вкладку **«Вид ресурсов».** В обзоре ресурсов дважды нажмите на `IDD_MFC01_DIALOG`. Диалогный ресурс отображается в редакторе ресурсов. Затем дважды щелкните кнопку OK.

Определите обработчик следующим образом.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>Пример

И добавьте следующую строку к реализации BOOL CMFC01Dlg::OnInitDialog().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Теперь можно выполнить сборку и запуск приложения. Обратите внимание, что любой текст в текстовом поле будет отображаться в всплывающем окне сообщения, когда приложение закрывается.

## <a name="see-also"></a>См. также раздел

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
