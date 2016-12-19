---
title: "CIPAddressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CIPAddressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIPAddressCtrl class"
  - "стандартные элементы управления, Internet Explorer 4.0"
  - "Internet address edit box"
  - "Internet Explorer 4.0 common controls"
  - "Internet protocol address box"
  - "IP address control"
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CIPAddressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления IP\-адрес Windows общего.  
  
## Синтаксис  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CIPAddressCtrl::CIPAddressCtrl](../Topic/CIPAddressCtrl::CIPAddressCtrl.md)|Создает объект `CIPAddressCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CIPAddressCtrl::ClearAddress](../Topic/CIPAddressCtrl::ClearAddress.md)|Очищает содержимое элемента управления "IP\-адрес".|  
|[CIPAddressCtrl::Create](../Topic/CIPAddressCtrl::Create.md)|Создает элемент управления " IP\-адрес и вложение его к объекту `CIPAddressCtrl`.|  
|[CIPAddressCtrl::CreateEx](../Topic/CIPAddressCtrl::CreateEx.md)|Создает элемент управления "IP\-адрес" с заданными стилей расширенными Windows и вложение его к объекту `CIPAddressCtrl`.|  
|[CIPAddressCtrl::GetAddress](../Topic/CIPAddressCtrl::GetAddress.md)|Получает значения адреса для всех 4 полей в элементе управления ip\-адреса.|  
|[CIPAddressCtrl::IsBlank](../Topic/CIPAddressCtrl::IsBlank.md)|Указывает, все поля в элементе управления "IP\-адрес" пуст.|  
|[CIPAddressCtrl::SetAddress](../Topic/CIPAddressCtrl::SetAddress.md)|Задает значения адреса для всех 4 полей в элементе управления ip\-адреса.|  
|[CIPAddressCtrl::SetFieldFocus](../Topic/CIPAddressCtrl::SetFieldFocus.md)|Устанавливает фокус ввода к указанному полю в элементе управления "IP\-адрес".|  
|[CIPAddressCtrl::SetFieldRange](../Topic/CIPAddressCtrl::SetFieldRange.md)|Устанавливает расстояние в указанном поле в элементе управления "IP\-адрес".|  
  
## Заметки  
 Элемент управления " IP\-адрес, элемент управления, аналогичный элемент управления "Поле ввода", позволяет ввести и управлять числовой адрес в формате протокола IP \(IP\).  
  
 Этот элемент управления \(и, следовательно, класс `CIPAddressCtrl` \) доступны только для программ, выполняемых в рамках Microsoft Internet Explorer 4.0 и более поздних версий.  Они также будут доступны под будущими версиями Windows и Windows NT.  
  
 Общие сведения об управлении IP\-адрес см. в разделе [Элементы управления "IP\-адрес"](http://msdn.microsoft.com/library/windows/desktop/bb761372) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CIPAddressCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)