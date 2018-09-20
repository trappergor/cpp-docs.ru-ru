---
title: 'Практическое: привязка данных DDX-DDV к элементам Управления Windows Forms | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87e6eb6e845a7e900568494ed2834f23b9f6c175
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418057"
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) вызовы [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) для создания элемента управления, соответствующие идентификатор элемента управления ресурса Если вы используете `DDX_ManagedControl` для `CWinFormsControl` управления (в код, созданный мастером), не следует вызывать `CreateManagedControl` явным образом для одного элемента управления.

Вызовите `DDX_ManagedControl` в [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) для создания элементов управления из идентификаторов ресурсов. Для обмена данными вы не обязательно должны использовать функции DDX/DDV к элементам Управления с помощью элементов управления Windows Forms. Вместо этого можно разместить код для доступа к свойствам управляемого элемента управления в `DoDataExchange` метод класса диалогового окна (или представления), как показано в следующем примере.

Приведенный ниже показано, как выполнить привязку строки C++ к пользовательскому элементу управления .NET.

## <a name="example"></a>Пример

Ниже приведен пример привязка данных DDX/DDV строки MFC `m_str` с определяемыми пользователем `NameText` свойства пользовательского элемента управления .NET.

Элемент управления создается [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызовы `CMyDlg::DoDataExchange` в первый раз, поэтому любой код, ссылающийся на `m_UserControl` должен следовать после `DDX_ManagedControl` вызова.

Этот код можно реализовать в приложении MFC01, созданный в [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

Поместите следующий код в объявлении CMFC01Dlg добавьте:

```
class CMFC01Dlg : public CDialog
{
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;
   CString m_str;
};
```

## <a name="example"></a>Пример

Поместите следующий код в реализации CMFC01Dlg добавьте:

```
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

Теперь мы добавим метод обработчика события щелчка кнопки "ОК". Нажмите кнопку **представление ресурсов** вкладки. В представлении ресурсов, дважды щелкните `IDD_MFC01_DIALOG`. Ресурс диалогового окна откроется в редакторе ресурсов. Затем дважды нажмите кнопку "ОК"...

Определите обработчик следующим образом.

```
void CMFC01Dlg::OnBnClickedOk()
{
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));
   OnOK();
}
```

## <a name="example"></a>Пример

И добавьте следующую строку в реализацию BOOL CMFC01Dlg::OnInitDialog().

```
m_MyControl.GetControl()->textBox1->Text = "hello";
```

Теперь можно построить и запустить приложение. Обратите внимание на то, что любой текст в текстовом поле будет отображаться в окне всплывающего сообщения при закрытии приложения.

## <a name="see-also"></a>См. также

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)<br/>
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)<br/>
[CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)