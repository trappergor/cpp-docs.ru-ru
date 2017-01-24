---
title: "Класс CNetAddressCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CNetAddressCtrl"
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: 32
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CNetAddressCtrl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CNetAddressCtrl` представляет элемент управления сетевого адреса, которое можно использовать для входных, так и проверять формат IPv4, IP версии 6 и именованных адресов DNS.  
  
## Синтаксис  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CNetAddressCtrl::CNetAddressCtrl](../Topic/CNetAddressCtrl::CNetAddressCtrl.md)|Создает объект `CNetAddressCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CNetAddressCtrl::Create](../Topic/CNetAddressCtrl::Create.md)|Создает элемент управления сетевого адреса с указанными стилями и вложение его к текущему объекту `CNetAddressCtrl`.|  
|[CNetAddressCtrl::CreateEx](../Topic/CNetAddressCtrl::CreateEx.md)|Создает элемент управления сетевого адреса с указанными расширенных стилей и вложение его к текущему объекту `CNetAddressCtrl`.|  
|[CNetAddressCtrl::DisplayErrorTip](../Topic/CNetAddressCtrl::DisplayErrorTip.md)|Отображает всплывающую подсказку ошибки, если пользователь вводит неподдерживаемый сетевой адрес в элемент управления адреса текущей сети.|  
|[CNetAddressCtrl::GetAddress](../Topic/CNetAddressCtrl::GetAddress.md)|Извлекает включен и проанализированное представление сетевого адреса, связанного с элементом управления сетевого адреса текущей.|  
|[CNetAddressCtrl::GetAllowType](../Topic/CNetAddressCtrl::GetAllowType.md)|Извлекает тип сетевого адреса, элемент управления сетевого адреса текущей может поддерживать.|  
|[CNetAddressCtrl::SetAllowType](../Topic/CNetAddressCtrl::SetAllowType.md)|Задает тип сетевого адреса, элемент управления сетевого адреса текущей может поддерживать.|  
  
## Заметки  
 Элемент управления сетевого адреса проверяет правильность формата адреса ввод пользователя.  Элемент управления не подключается к сетевому адресу.  Метод [CNetAddressCtrl::SetAllowType](../Topic/CNetAddressCtrl::SetAllowType.md) указывает один или несколько типов адреса, метод [CNetAddressCtrl::GetAddress](../Topic/CNetAddressCtrl::GetAddress.md) может проанализировать и проверки.  Адрес может быть в формате IPv4, IP версии 6 или именованного адреса сервера сети узла или назначения широковещательного сообщения.  Если формат адресов неверен, то можно использовать метод [CNetAddressCtrl::DisplayErrorTip](../Topic/CNetAddressCtrl::DisplayErrorTip.md) для отображения окна сообщения подсказки, графически указывающий к текстовому полю управления сетевого адреса и отображает стандартное сообщение об ошибке.  
  
 Класс `CNetAddressCtrl` является производным от класса [CEdit](../Topic/CEdit%20Class.md).  Следовательно, элемент управления сетевого адреса предоставляет доступ ко всем сообщениям элемента управления "Поле ввода" Windows.  
  
 Следующая диаграмма отображает диалоговое окно, содержащее элемент управления сетевого адреса.  Текстовое поле \(1\) для управления сетевого адреса содержит недопустимый сетевой адрес.  Сообщение подсказки \(2\) отображается, если сетевой адрес недопустим.  
  
 ![Диалог с элементом управления сетевым адресом и подсказкой.](../../mfc/reference/media/cnetaddctrl.png "CNetAddCtrl")  
  
## Пример  
 Следующий пример кода представляет собой часть диалогового окна, которое проверяет сетевой адрес.  Обработчики событий для переключателей 3 указывают, что сетевой адрес может иметь один из 3 типов адреса.  Вводе пользователем адреса в текстовом поле управления сети, а затем нажимает кнопку, чтобы проверить адрес.  Если адрес является допустимым, то сообщение об успешном выполнении отображается; в противном случае – стандартное сообщение об ошибке подсказки.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/CPP/cnetaddressctrl-class_1.cpp)]  
  
## Пример  
 В следующем примере кода из файла заголовка диалогового окна определяет переменные [NC\_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) и [NET\_ADDRESS\_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/bb773346), которые должны быть методом [CNetAddressCtrl::GetAddress](../Topic/CNetAddressCtrl::GetAddress.md).  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/CPP/cnetaddressctrl-class_2.h)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CEdit](../Topic/CEdit%20Class.md)  
  
 `CNetAddressCtrl`  
  
## Требования  
 **заголовок:** afxcmn.h  
  
 Этот класс поддерживается в [!INCLUDE[windowsver](../Token/windowsver_md.md)] и более поздних версиях.  
  
 Дополнительные требования для этого класса см. в [Требования к сборке для использования стандартных элементов управления в Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
## См. также  
 [CNetAddressCtrl Class](../../mfc/reference/cnetaddressctrl-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../Topic/CEdit%20Class.md)