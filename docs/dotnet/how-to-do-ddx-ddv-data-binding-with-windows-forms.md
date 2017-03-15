---
title: "Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC [C++], размещение элемента управления Windows Forms"
  - "Windows Forms [C++], поддержка MFC"
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Практическое руководство. Привязка данных DDX/DDV к элементам управления Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[DDX\_ManagedControl](../Topic/DDX_ManagedControl.md) вызывает метод [CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md) для создания элемента управления, соответствующего идентификатору элемента управления ресурса.  Если функция `DDX_ManagedControl` используется для элемента управления `CWinFormsControl` \(в коде, созданном мастером\), не следует напрямую вызывать метод `CreateManagedControl` для этого же элемента управления.  
  
 Следует вызвать функцию `DDX_ManagedControl` в [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) для создания элементов управления на основе идентификатора ресурса.  Для обмена данными необязательно использовать функции DDX\/DDV с элементами управления Windows Forms.  Вместо этого можно разместить код для получения доступа к свойствам управляемого элемента управления в методе `DoDataExchange` класса диалогового окна \(или представления\), как в следующем примере.  
  
 В следующем примере показано, как выполнить привязку строки C\+\+ к пользовательскому элементу управления .NET.  
  
## Пример  
 В следующем примере демонстрируется привязка данных DDX\/DDV строки MFC `m_str` к определенному пользователем свойству `NameText` пользовательского элемента управления .NET.  
  
 Элемент управления создается, когда метод [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md) в первый раз вызывает метод `CMyDlg::DoDataExchange`, поэтому любой другой код, ссылающийся на элемент управления `m_UserControl`, должен располагаться после вызова `DDX_ManagedControl`.  
  
 Этот код можно реализовать в приложении MFC01, созданном в разделе [Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
 В разделе объявлений CMFC01Dlg добавьте следующий код:  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## Пример  
 В разделе реализации CMFC01Dlg добавьте следующий код:  
  
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
  
## Пример  
 Теперь следует добавить метод обработчика события нажатия кнопки "ОК".  Выберите вкладку **Ресурсы**.  На вкладке "Ресурсы" дважды щелкните объект `IDD_MFC01_DIALOG`.  В редакторе ресурсов появится ресурс диалогового окна.  Дважды нажмите кнопку "ОК".  
  
 Определите обработчик следующим образом.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## Пример  
 В разделе реализации BOOL CMFC01Dlg::OnInitDialog\(\) добавьте следующую строку.  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 Теперь можно выполнить построение и запустить приложение.  Обратите внимание, что при закрытии приложения любой текст в текстовом поле отображается в всплывающем окне сообщения.  
  
## См. также  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md)   
 [DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)