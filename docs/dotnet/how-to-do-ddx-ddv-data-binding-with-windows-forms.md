---
title: Практическое руководство. Привязка данных DDX-DDV к элементам управления Windows Forms
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
ms.openlocfilehash: a0759eba1c55e72f2c0a99964b0b2d254df82a25
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008317"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) вызывает метод [Квинформсконтрол:: креатеманажедконтрол](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) , чтобы создать элемент управления, соответствующий идентификатору элемента управления ресурса. При использовании `DDX_ManagedControl` для `CWinFormsControl` элемента управления (в коде, созданном мастером) не следует вызывать `CreateManagedControl` явно для того же элемента управления.

Вызов `DDX_ManagedControl` в [CWnd::D одатаексчанже](../mfc/reference/cwnd-class.md#dodataexchange) для создания элементов управления из идентификаторов ресурсов. Для обмена данными не нужно использовать функции DDX/DDV с элементами управления Windows Forms. Вместо этого можно поместить код для доступа к свойствам управляемого элемента управления в `DoDataExchange` методе вашего диалогового окна (или представления), как показано в следующем примере.

В следующем примере показано, как привязать собственную строку C++ к пользовательскому элементу управления .NET.

## <a name="example-ddxddv-data-binding"></a>Пример: привязка данных DDX/DDV

Ниже приведен пример привязки данных DDX/DDV к строке MFC `m_str` с определяемым пользователем `NameText` свойством пользовательского элемента управления .NET.

Элемент управления создается при первом вызове метода [CDialog:: онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog) `CMyDlg::DoDataExchange` , поэтому любой код, на который ссылается, `m_UserControl` должен следовать после `DDX_ManagedControl` вызова.

Этот код можно реализовать в приложении MFC01, созданном в [процедуре Создание пользовательского элемента управления и узла в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

Добавьте следующий код в объявление CMFC01Dlg:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example-implement-dodataexchange"></a>Пример. Реализация DoDataExchange ()

Добавьте следующий код в реализацию CMFC01Dlg:

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

## <a name="example-add-handler-method"></a>Пример: Добавление метода обработчика

Теперь мы добавим метод обработчика для нажатия кнопки ОК. Перейдите на вкладку **представление ресурсов** . В представление ресурсов дважды щелкните `IDD_MFC01_DIALOG` . В редакторе ресурсов откроется диалоговое окно ресурс. Затем дважды щелкните кнопку ОК.

Определите обработчик следующим образом.

```cpp
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example-set-the-textbox-text"></a>Пример. установка текста текстового поля

И добавьте следующую строку в реализацию BOOL CMFC01Dlg:: Онинитдиалог ().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Теперь можно выполнить сборку и запуск приложения. Обратите внимание, что любой текст в текстовом поле будет отображаться во всплывающем окне сообщения при закрытии приложения.

## <a name="see-also"></a>См. также статью

[Класс Квинформсконтрол](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)
