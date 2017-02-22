---
title: "CWinFormsControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsControl class"
  - "MFC [C++], поддержка Windows Forms"
  - "Windows Forms [C++], поддержка MFC"
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CWinFormsControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет базовую функциональность для размещения элементов управления Windows Forms.  
  
## Синтаксис  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### Параметры  
 `TManagedControl`  
 Управление платформы .NET Framework Windows Forms для отображения в приложении MFC.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinFormsControl::CWinFormsControl](../Topic/CWinFormsControl::CWinFormsControl.md)|Создает объект программы\-оболочки элемента управления MFC Windows Forms.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)|Создание элемента управления Windows Forms в контейнере MFC.|  
|[CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)|Извлекает указатель к элементу управления Windows Forms.|  
|[CWinFormsControl::GetControlHandle](../Topic/CWinFormsControl::GetControlHandle.md)|Получает дескриптор к элементу управления Windows Forms.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinFormsControl::operator \-\>](../Topic/CWinFormsControl::operator%20-%3E.md)|Заменяет [CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md) в выражениях.|  
|[CWinFormsControl::operator TManagedControl^](../Topic/CWinFormsControl::operator%20TManagedControl%5E.md)|Приводит тип как указатель к элементу управления Windows Forms.|  
  
## Заметки  
 Класс `CWinFormsControl` предоставляет базовую функциональность для размещения элементов управления Windows Forms.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Код MFC не должен кэшировать дескрипторы окна \(обычно, хранящихся в `m_hWnd`\).  Некоторые свойства элементов управления Windows Forms требуется, чтобы базовое Win32 `Window` было удалено, и создается повторно с помощью `DestroyWindow` и `CreateWindow`.  Реализация Windows Forms в MFC обрабатываются события `Destroy` и `Create` элементов управления, чтобы обновить элемент `m_hWnd`.  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC \(в соответствии с AFXDLL\), которое.  
  
## Требования  
 **заголовок:** afxwinforms.h  
  
## См. также  
 [CWinFormsDialog Class](../Topic/CWinFormsDialog%20Class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)