---
title: Размещение Windows форме пользовательский элемент управления в диалоговом окне MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], hosting as MFC Dialog
- hosting Windows Forms control [C++]
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b356bff4974b43445524d9bc07e1e37c62a6f8d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138682"
---
# <a name="hosting-a-windows-form-user-control-as-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
MFC предоставляет класс шаблона [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) , чтобы можно было разместить пользовательский элемент управления Windows Forms (<xref:System.Windows.Forms.UserControl>) в модальные и немодальные диалоговом окне MFC. `CWinFormsDialog` является производным от класса MFC [CDialog](../mfc/reference/cdialog-class.md), поэтому в диалоговом окне могут запускаться как модальное или немодальный.  
  
 Процесс, `CWinFormsDialog` , который используется для размещения элемента управления пользователя аналогична описанной в [размещение пользовательского элемента управления формы Windows в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md). Однако `CWinFormsDialog` управляет инициализацией и размещением пользовательского элемента управления, чтобы не должен быть запрограммирован вручную.  
  
 Образец приложения Windows Forms используются с MFC, в разделе [MFC и интеграция с Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Создайте проект приложения MFC.  
  
     На **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**. В **Visual C++** выберите **приложение MFC**.  
  
     В **имя** введите `MFC03` и измените параметр решения для **добавить решение**. Нажмите кнопку **ОК**.  
  
     В **мастер приложений MFC**, примите параметры по умолчанию и нажмите кнопку **Готово**. Это создает приложение MFC с интерфейсом MDI.  
  
2.  Настройте проект.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши **MFC03** узел проекта и выберите **свойства**. **Страницы свойств** откроется диалоговое окно.  
  
     В **страницы свойств** диалогового **свойства конфигурации** дерева, выберите **Общие**, а затем в **проекта по умолчанию**установите **поддержки Common Language Runtime** для **поддержка среды CLR (/ clr)**. Нажмите кнопку **ОК**.  
  
3.  Добавьте ссылку на элемент управления .NET.  
  
     В **обозревателе решений**, щелкните правой кнопкой мыши **MFC03** узел проекта и выберите **добавить**, **ссылки**. В **страницу свойств**, нажмите кнопку **добавить новую ссылку**, выберите проект WindowsControlLibrary1 (под **проекты** вкладку) и нажмите кнопку **ОК**. Добавлена ссылка в виде [/FU](../build/reference/fu-name-forced-hash-using-file.md) компилятора параметр, чтобы программа будет компилироваться; также он копирует WindowsControlLibrary1.dll в `MFC03` проект каталогов, чтобы программа будет запущена.  
  
4.  Добавить `#include <afxwinforms.h>` на stdafx.h в конце существующего `#include` инструкции.  
  
5.  Добавьте новый класс, который наследуется от класса `CDialog`.  
  
     Щелкните правой кнопкой мыши имя проекта и Добавление класса MFC (вызываемой класс CHostForWinForm), который наследуется от класса `CDialog`. Так как ресурс диалогового окна не требуется, можно удалить идентификатор ресурса (выберите представление ресурсов, разверните папку диалоговое окно и удалить идентификатор ресурса.  Удалите все ссылки на идентификатор в коде.).  
  
6.  Замените `CDialog` в файлах CHostForWinForm.h и CHostForWinForm.cpp с `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.  
  
7.  Вызовите DoModal класс CHostForWinForm класса.  
  
     Добавьте в MFC03.cpp `#include "HostForWinForm.h"`.  
  
     Прежде чем оператор return в определении CMFC03App::InitInstance добавьте:  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  Постройте и запустите проект.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, нажмите кнопку **Запуск без отладки**.  
  
     Затем добавляется код для отслеживания состояния элемента управления в формах Windows Forms из приложения MFC.  
  
9. Добавьте обработчик для OnInitDialog.  
  
     Отображение **свойства** окна (F4). В **представление классов**, выберите класс CHostForWinForm. В **свойства** выберите переопределяет и в строке OnInitDialog, щелкните в левом столбце и выберите \< Добавить >. Это добавляет CHostForWinForm.h следующую строку:  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. Задайте OnInitDialog (в CHostForWinForm.cpp) следующим образом:  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. Затем добавьте обработчик событий OnButton1. Добавьте следующие строки в раздел открытый класс CHostForWinForm класса в CHostForWinForm.h:  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     В CHostForWinForm.cpp добавьте это определение:  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. Постройте и запустите проект. При нажатии кнопки, которая находится на форме Windows Forms, будет выполняться код в приложении MFC.  
  
     Затем добавляется код для отображения кода MFC значения в текстовом поле на форме Windows Forms.  
  
13. В разделе открытый класс CHostForWinForm класса в CHostForWinForm.h добавьте следующее объявление:  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. В определении DoDataExchange в CHostForWinForm.cpp добавьте следующие три строки в конец функции:  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. В определении событий OnButton1 в CHostForWinForm.cpp добавьте следующие три строки в конец функции:  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. Постройте и запустите проект.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)