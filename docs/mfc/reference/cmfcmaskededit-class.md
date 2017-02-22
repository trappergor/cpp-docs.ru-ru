---
title: "CMFCMaskedEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMaskedEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMaskedEdit class"
  - "CMFCMaskedEdit constructor"
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCMaskedEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCMaskedEdit` поддерживает замаскированный элемент управления "Поле ввода", который проверяет ввод пользователя и маски и отображает результаты отмеченные в соответствии с шаблоном.  
  
## Синтаксис  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Конструктор по умолчанию.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMaskedEdit::DisableMask](../Topic/CMFCMaskedEdit::DisableMask.md)|Запрещает проверку вводимых пользователем данных.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableGetMaskedCharsOnly.md)|Определяет, является ли метод `GetWindowText` извлекает только замаскированные символы.|  
|[CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md)|Инициализирует замаскированный элемент управления "Поле ввода".|  
|[CMFCMaskedEdit::EnableSelectByGroup](../Topic/CMFCMaskedEdit::EnableSelectByGroup.md)|Определяет, выбран замаскированный элемент управления "Поле ввода", заданные группы в составе ввод данных пользователем или все входные данные пользователя.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](../Topic/CMFCMaskedEdit::EnableSetMaskedCharsOnly.md)|Определяет, является ли текст в проверено только замаскированных символов или для маски целого.|  
|`CMFCMaskedEdit::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md)|Извлечение отмеченные вставке СМС с маской из элемента управления "Поле ввода".|  
|[CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md)|Указывает строку допустимых символов, которые пользователь может ввести.|  
|[CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md)|Отображает запрос в замаскированном элементе управления "Поле ввода".|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMaskedEdit::IsMaskedChar](../Topic/CMFCMaskedEdit::IsMaskedChar.md)|Вызываемый платформой для проверки указанный символ для соответствующего знака маски.|  
  
## Заметки  
 Выполните следующие действия для использования элемента управления `CMFCMaskedEdit` в приложении:  
  
 1.  Внедрение объект `CMFCMaskedEdit` в класс окна.  
  
 2.  Вызовите метод [CMFCMaskedEdit::EnableMask](../Topic/CMFCMaskedEdit::EnableMask.md) чтобы указать маску.  
  
 3.  Вызовите метод [CMFCMaskedEdit::SetValidChars](../Topic/CMFCMaskedEdit::SetValidChars.md) чтобы указать список допустимых символов.  
  
 4.  Вызовите метод [CMFCMaskedEdit::SetWindowText](../Topic/CMFCMaskedEdit::SetWindowText.md), чтобы указать текст по умолчанию для элемента управления "Поле ввода" с маской.  
  
 5.  Вызовите метод [CMFCMaskedEdit::GetWindowText](../Topic/CMFCMaskedEdit::GetWindowText.md) для получения включен текст.  
  
 Если не вызвать один или несколько методов для инициализации маска, допустимые знаки и текст по умолчанию, то замаскированный элемент управления "Поле ввода" ведет себя как обычный элемент управления "Поле ввода" ведет себя.  
  
## Пример  
 В следующем примере показано, как настроить маску \(например номер телефона\) с помощью метода `EnableMask` для создания маска для элемента управления "Поле ввода" с маской, метода `SetValidChars` для идентификации строки допустимых символов, которые пользователь может вводить и метода `SetWindowText` для отображения подсказки в замаскированном элементе управления "Поле ввода".  Данный пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/CPP/cmfcmaskededit-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CEdit](../Topic/CEdit%20Class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## Требования  
 **заголовок:** afxmaskededit.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CEdit Class](../Topic/CEdit%20Class.md)