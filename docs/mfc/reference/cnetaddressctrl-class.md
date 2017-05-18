---
title: "Класс CNetAddressCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl class
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 03b08d13a9e456c5533b4dddce7f389a63a69c6d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cnetaddressctrl-class"></a>Класс CNetAddressCtrl
Класс `CNetAddressCtrl` представляет элемент управления сетевого адреса, который можно использовать для ввода и проверки формата IPv4, IPv6 и именованных адресов DNS.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Создает объект `CNetAddressCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|Создает элемент управления network address с указанным стилем и присоединяет его к текущему `CNetAddressCtrl` объекта.|  
|[CNetAddressCtrl::CreateEx](#createex)|Создает элемент управления network address с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Отображает всплывающую подсказку ошибки при вводе адреса не поддерживаются в текущей управления сетевым адресом.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|Возвращает представление проверяются и разбора сетевой адрес, связанный с текущей управления сетевым адресом.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Получает тип сетевой адрес, может поддерживать текущего управления сетевым адресом.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Задает тип сетевой адрес, может поддерживать текущего управления сетевым адресом.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления сетевого адреса проверяет правильность формата адреса, который вводит пользователь. Элемент управления не на самом деле подключиться к сетевой адрес. [CNetAddressCtrl::SetAllowType](#setallowtype) метод указывает один или несколько типов адресов, [CNetAddressCtrl::GetAddress](#getaddress) метод можно проанализировать и проверить. Адрес может быть в формате IPv4, IPv6 или для сервера, сети, узла или назначения широковещательное сообщение с указанным адресом. Неправильный формат адреса, можно использовать [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить окно сообщения подсказку графически в текстовое поле элемент управления сетевого адреса и отображает сообщение об ошибке стандартных.  
  
 `CNetAddressCtrl` Класс является производным от [CEdit](../../mfc/reference/cedit-class.md) класса. Таким образом элемент управления сетевого адреса предоставляет доступ ко всем сообщениям управления редактирования Windows.  
  
 На следующем рисунке показано диалоговое окно, содержащее управления сетевым адресом. Текстовое поле (1) для управления сетевым адресом содержит недопустимый сетевой адрес. Если Недопустимый сетевой адрес, отображается всплывающая подсказка сообщение (2).  
  
 ![Диалоговое окно с элементом управления сетевым адресом и подсказкой. ] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>Пример  
 В следующем примере кода является часть диалогового окна, которое проверяет сетевой адрес. Обработчики событий для трех переключателей укажите, что сетевой адрес может быть один из трех типов адресов. Пользователь вводит в текстовом поле элемент управления сетевого адреса, а затем нажимает кнопку для проверки адреса. Если адрес является допустимым, отображается сообщение об успешном выполнении; в противном случае — отображается сообщение об ошибке предопределенные подсказку.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода из файла заголовка диалогового окна определяется [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) и [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) переменных, которые требуются [CNetAddressCtrl::GetAddress](#getaddress) метод.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
 Этот класс поддерживается в [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] и более поздних версий.  
  
 Дополнительные требования к этому классу, описаны в [построения требования для Windows Vista Общие элементы управления](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl  
 Создает объект `CNetAddressCtrl`.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::Create](#create) или [CNetAddressCtrl::CreateEx](#createex) способ создания элемента управления сети и присоединить его к `CNetAddressCtrl` объекта.  
  
##  <a name="create"></a>CNetAddressCtrl::Create  
 Создает элемент управления network address с указанным стилем и присоединяет его к текущему `CNetAddressCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwStyle`|Побитовое сочетание стили, применяемые к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/edit-styles.md).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
##  <a name="createex"></a>CNetAddressCtrl::CreateEx  
 Создает элемент управления network address с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwExStyle`|Побитовое сочетание (или) расширенных стилей применяется к элементу управления. Дополнительные сведения см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции.|  
|[in] `dwStyle`|Побитовое сочетание (или) стилей применяется к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/edit-styles.md).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
##  <a name="displayerrortip"></a>CNetAddressCtrl::DisplayErrorTip  
 Отображает сообщение об ошибке в всплывающей подсказки, связанный с текущей управления сетевым адресом.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `S_OK` , если этот метод выполнен успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод для указания типов адресов, которые может поддерживать текущего управления сетевым адресом. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и анализа сетевого адреса, введенного пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку ошибки сообщения, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Это сообщение вызывает [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) макрос, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Отправляет этот макрос `NCM_DISPLAYERRORTIP` сообщение.  
  
##  <a name="getaddress"></a>CNetAddressCtrl::GetAddress  
 Возвращает представление проверяются и разбора сетевой адрес, связанный с текущей управления сетевым адресом.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in, out] `pAddress`|Указатель на [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) структуры.  Задайте `pAddrInfo` члена структуры по адресу [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) структуры перед вызовом метода GetAddress.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `S_OK` , если этот метод выполнен успешно; в противном случае — код ошибки COM. Дополнительные сведения о кодах возможных ошибок, ознакомьтесь с разделом возвращают значение [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) макрос.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод выполнен успешно, [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) структура содержит дополнительные сведения о сетевом адресе.  
  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод для указания типов адресов может поддерживать текущего управления сетевым адресом. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и анализа сетевого адреса, введенного пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку ошибки сообщения, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Этот метод вызывает [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) макрос, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Отправляет этот макрос `NCM_GETADDRESS` сообщение.  
  
##  <a name="getallowtype"></a>CNetAddressCtrl::GetAllowType  
 Получает тип сетевой адрес, может поддерживать текущего управления сетевым адресом.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание (или) флагов, указывающее типы адресов может поддерживать элемент управления сетевого адреса. Дополнительные сведения см. в разделе [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).  
  
### <a name="remarks"></a>Примечания  
 Это сообщение вызывает [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) макрос, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Отправляет этот макрос `NCM_GETALLOWTYPE` сообщение.  
  
##  <a name="setallowtype"></a>CNetAddressCtrl::SetAllowType  
 Задает тип сетевой адрес, может поддерживать текущего управления сетевым адресом.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwAddrMask`|Побитовое сочетание (или) флагов, указывающее типы адресов может поддерживать элемент управления сетевого адреса. Дополнительные сведения см. в разделе [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если этот метод выполнен успешно; в противном случае — код ошибки COM.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод для указания типов адресов, которые может поддерживать текущего управления сетевым адресом. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и анализа сетевого адреса, введенного пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку ошибки сообщения, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Это сообщение вызывает [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) макрос, который описан в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Отправляет этот макрос `NCM_SETALLOWTYPE` сообщение.  
  
## <a name="see-also"></a>См. также  
 [Класс CNetAddressCtrl](../../mfc/reference/cnetaddressctrl-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)

