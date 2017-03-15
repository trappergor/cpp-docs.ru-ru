---
title: "VSZ-файл (элемент управления проекта) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VSZ-файлы"
  - "пользовательские мастера, .VSZ-файлы"
  - "пользовательские мастера, файлы элементов управления проектами"
  - "файлы [C++], созданные мастером пользователя"
  - "VSZ-файлы"
ms.assetid: b8678fee-6795-46d1-9338-48b22d5e9207
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VSZ-файл (элемент управления проекта)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отправной точкой любого мастера является VSZ\-файл.  VSZ\-файл представляет собой текстовый файл, определяющий мастер, который требуется вызвать, и передаваемые этому мастеру данные.  Файл содержит двухстрочный заголовок, за которым следуют различные необязательные параметры, которые должны быть переданы мастеру.  Список необязательных параметром см. в разделе [Предопределенные символы специального мастера](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
 В следующем примере показан заголовок VSZ\-файла.  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine.10.0  
Param="WIZARD_NAME = My AppWizard"  
```  
  
-   Первая строка заголовка указывает номер версии формата файла шаблона.  Можно задать следующие числа: `6.0`, `7.0` или `7.1`.  Другие числа не допускаются, и их использование приведет к возникновению ошибки "Недопустимый формат".  
  
-   Вторая строка присваивает для переменной **Wizard** идентификатор ProgID мастера, созданного средой Visual Studio.  Идентификатор ProgID является строковым представлением идентификатора CLSID, например `VsWizard.VsWizardEngine.10.0`.  
  
     Если в мастере имеется пользовательский интерфейс, идентификатор ProgID автоматически указывает мастеру на необходимость реализации интерфейса <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>.  По умолчанию методы данного интерфейса используются в [HTM\-файлах](../ide/html-files.md) проекта.  Можно изменить поведение мастера посредством использования методов для этого интерфейса в HTM\-файлах.  Дополнительные сведения см. в описании класса <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>, который является компонентным классом для интерфейса <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>.  
  
-   За двумя первыми строками следует необязательный список параметров, который позволяет VSZ\-файлу передавать дополнительные настраиваемые параметры в мастер.  Каждое значение передается мастеру как строковый элемент в массиве значений типа Variant в методе <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> элемента управления.  По умолчанию мастер с пользовательским интерфейсом производит следующие параметры по умолчанию:  
  
    ```  
    Param="START_PATH = <path to the wizard>"  
    Param="HTML_PATH = <path to the wizard's HTML file>"  
    Param="TEMPLATES_PATH = <path to the wizard's template file>"  
    Param="SCRIPT_PATH = <path to the wizard's script files>"  
    Param="IMAGES_PATH = <path to the wizard's images>"  
    ```  
  
     Если мастер не имеет пользовательского интерфейса, он не имеет также параметра `IMAGES_PATH` и вместо него содержит следующие параметры:  
  
    ```  
    Param="WIZARD_UI = FALSE"  
    Param="SOURCE_FILTER = txt"  
    ```  
  
-   VSZ\-файл может содержать следующие параметры, которые указывают функции, находящиеся в файле [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md):  
  
    ```  
    Param="PREPROCESS_FUNCTION = CanAddATLClass"  
    Param="PREPROCESS_FUNCTION = CanAddMFCClass"  
    Param="PREPROCESS_FUNCTION = CanAddClass"  
    ```  
  
 Функции[CanAddATLClass](../ide/canaddatlclass.md), [CanAddMFCClass](../ide/canaddmfcclass.md) и [CanAddClass](../ide/canaddclass.md) вызываются мастером для подтверждения доступности [Модели кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  Если одна функция возвращает значение **false**, мастер не запускается.  
  
 Можно добавить мастер на панель шаблонов в диалоговом окне **Новый проект** в Visual Studio, поместив файл VSZ в каталог "vcprojects".  По умолчанию, специальный мастер записывает VSZ\-файл в этот каталог.  
  
> [!NOTE]
>  Если удалить файлы и каталоги мастера, следует также удалить файлы проекта с расширением VSZ, VSDIR и ICO из каталога "vcprojects".  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Visual C\+\+ Wizard Model](http://msdn.microsoft.com/ru-ru/159395ac-33c7-47bf-ad42-4e1435ddc758)   
 [Добавление мастеров в диалоговые окна "Добавить элемент" и "Создать проект" при помощи файлов VSDIR](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)