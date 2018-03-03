---
title: "Как: привязка данных DDX DDV Windows Forms | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], hosting a Windows Forms Control
- Windows Forms [C++], MFC support
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9996fd10bad8578bd70739aa10b863bcea7f3c18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-do-ddxddv-data-binding-with-windows-forms"></a>Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms
[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol) вызовы [CWinFormsControl::CreateManagedControl](../mfc/reference/cwinformscontrol-class.md#createmanagedcontrol) для создания элемента управления, сопоставление идентификатора элемента управления ресурса Если вы используете `DDX_ManagedControl` для `CWinFormsControl` управления (в код, созданный мастером), не следует вызывать `CreateManagedControl` явным образом для того же элемента управления.  
  
 Вызовите `DDX_ManagedControl` в [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) для создания элементов управления из идентификаторы ресурсов. Для обмена данными необязательно использовать функции DDX/DDV с элементами управления Windows Forms. Вместо этого можно поместить код для доступа к свойствам управляемого элемента управления в `DoDataExchange` метод класса диалогового окна (или представления), как показано в следующем примере.  
  
 Приведенный ниже показано, как выполнить привязку строки C++ к пользовательскому элементу управления .NET.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример привязка данных DDX/DDV строки MFC `m_str` с определяемой пользователем `NameText` свойство пользовательского элемента управления .NET.  
  
 Элемент управления создается [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызовы `CMyDlg::DoDataExchange` в первый раз, так что любой код, который ссылается `m_UserControl` должен следовать после `DDX_ManagedControl` вызова.  
  
 Этот код можно реализовать в приложении MFC01, созданный в [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
 Поместите следующий код в объявление CMFC01Dlg добавьте:  
  
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
 Теперь мы будем добавлять метод обработчика события click кнопки «ОК». Нажмите кнопку **представление ресурсов** вкладки. В представлении ресурсов дважды щелкните `IDD_MFC01_DIALOG`. Ресурс диалогового окна откроется в редакторе ресурсов. Затем дважды нажмите кнопку "ОК"...  
  
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
  
 Теперь можно построить и запустить приложение. Обратите внимание, что любой текст в текстовом поле будет отображаться в всплывающее сообщение об ошибке при закрытии приложения.  
  
## <a name="see-also"></a>См. также  
 [Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)   
 [DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)   
 [CWnd::DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)