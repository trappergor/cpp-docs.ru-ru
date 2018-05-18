---
title: Класс CNetAddressCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c579f452f26761abd7b52c849fa0117a98777355
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CNetAddressCtrl::Create](#create)|Создает элемент управления сетевого адреса с указанным стилем и прикрепляет его к текущему `CNetAddressCtrl` объекта.|  
|[CNetAddressCtrl::CreateEx](#createex)|Создает элемент управления сетевого адреса с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Отображает ошибки всплывающая подсказка, когда пользователь вводит адрес сети не поддерживается в текущей управления сетевого адреса.|  
|[CNetAddressCtrl::GetAddress](#getaddress)|Извлекает проверяются и проанализированное представление сетевой адрес, связанный с текущей управления сетевого адреса.|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Возвращает тип сетевой адрес, который может поддерживать текущего управления сетевого адреса.|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Задает тип сетевой адрес, который может поддерживать текущего управления сетевого адреса.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления сетевого адреса проверяет правильность формата введенного адреса. Элемент управления не фактически подключиться к сетевой адрес. [CNetAddressCtrl::SetAllowType](#setallowtype) метод указывает один или несколько типов адреса, [CNetAddressCtrl::GetAddress](#getaddress) метода можно проанализировать и проверить. Адрес может быть в формате IPv4, IPv6 или с указанным адресом для сервера, сети, узла или назначение широковещательных сообщений. Неправильный формат адреса, можно использовать [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод Отображение окна сообщения подсказку, графически указывает на элемент управления сетевого адреса в текстовое поле и отображает предопределенного сообщение об ошибке.  
  
 `CNetAddressCtrl` Класс является производным от [CEdit](../../mfc/reference/cedit-class.md) класса. Следовательно элемент управления сетевого адреса предоставляет доступ к все сообщения управления редактирования Windows.  
  
 На следующем рисунке показано диалоговое окно, которое содержит элемент управления сетевого адреса. Текстовое поле (1) для управления сетевым адресом содержит недопустимый сетевой адрес. (2) сообщение всплывающая подсказка отображается в том случае, если сетевой адрес является недопустимым.  
  
 ![Диалоговое окно с элементом управления сетевым адресом и подсказкой. ] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>Пример  
 В следующем примере кода является частью диалоговое окно, которое проверяет сетевой адрес. Обработчики событий для трех переключателей укажите, что сетевой адрес может быть один из трех типов адресов. Пользователь вводит в текстовом поле элемент управления сетевого адреса, а затем нажимает кнопку для проверки адреса. Если адрес является недопустимым, отображается сообщение об успешном выполнении; в противном случае отображается сообщение об ошибке предопределенных всплывающая подсказка.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода из файла заголовка диалогового окна определяет [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) и [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) переменных, которые требуются [CNetAddressCtrl::GetAddress](#getaddress)метод.  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
 Этот класс поддерживается в [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] и более поздних версий.  
  
 Дополнительные требования к этому классу, описаны в [построения требования для общих элементов управления Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl  
 Создает объект `CNetAddressCtrl`.  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::Create](#create) или [CNetAddressCtrl::CreateEx](#createex) способ создания элемента управления сети и присоединить его к `CNetAddressCtrl` объекта.  
  
##  <a name="create"></a>  CNetAddressCtrl::Create  
 Создает элемент управления сетевого адреса с указанным стилем и прикрепляет его к текущему `CNetAddressCtrl` объекта.  
  
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
|[in] `dwStyle`|Побитовое сочетание стили, чтобы применить к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
##  <a name="createex"></a>  CNetAddressCtrl::CreateEx  
 Создает элемент управления сетевого адреса с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.  
  
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
|[in] `dwExStyle`|Побитовое сочетание (OR) расширенные стили, которые надо применить к элементу управления. Дополнительные сведения см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции.|  
|[in] `dwStyle`|Побитовое сочетание (OR) стили, чтобы применить к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip  
 Отображает сообщение об ошибке в всплывающей подсказки, связанный с текущей управления сетевого адреса.  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `S_OK` Если этот метод выполнен успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов, которые может поддерживать текущего управления сетевого адреса. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод, чтобы проверить и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку сообщение ошибки, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Это сообщение вызывает [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314) макросом, который описан в Windows SDK. Отправляет этого макроса `NCM_DISPLAYERRORTIP` сообщения.  
  
##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress  
 Извлекает проверяются и проанализированное представление сетевой адрес, связанный с текущей управления сетевого адреса.  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in, out] `pAddress`|Указатель на [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345) структуры.  Задать `pAddrInfo` член этой структуры на адрес [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) структуры перед вызовом метода GetAddress.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `S_OK` Если этот метод выполнен успешно; в противном случае — код ошибки COM. Дополнительные сведения о кодах возможных ошибок см. в разделе разделе возвращают значение [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) макрос.  
  
### <a name="remarks"></a>Примечания  
 В случае успешного выполнения [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) структура содержит дополнительные сведения о сетевой адрес.  
  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов может поддерживать текущего управления сетевого адреса. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод, чтобы проверить и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку сообщение ошибки, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Этот метод вызывает [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316) макросом, который описан в Windows SDK. Отправляет этого макроса `NCM_GETADDRESS` сообщения.  
  
##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType  
 Возвращает тип сетевой адрес, который может поддерживать текущего управления сетевого адреса.  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовое сочетание (OR) флагов, указывающее типы адресов может поддерживать элемент управления сетевого адреса. Дополнительные сведения см. в разделе [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).  
  
### <a name="remarks"></a>Примечания  
 Это сообщение вызывает [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318) макросом, который описан в Windows SDK. Отправляет этого макроса `NCM_GETALLOWTYPE` сообщения.  
  
##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType  
 Задает тип сетевой адрес, который может поддерживать текущего управления сетевого адреса.  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwAddrMask`|Побитовое сочетание (OR) флагов, указывающее типы адресов может поддерживать элемент управления сетевого адреса. Дополнительные сведения см. в разделе [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если этот метод выполнен успешно; в противном случае — код ошибки COM.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов, которые может поддерживать текущего управления сетевого адреса. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод, чтобы проверить и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить всплывающую подсказку сообщение ошибки, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.  
  
 Это сообщение вызывает [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320) макросом, который описан в Windows SDK. Отправляет этого макроса `NCM_SETALLOWTYPE` сообщения.  
  
## <a name="see-also"></a>См. также  
 [Класс CNetAddressCtrl](../../mfc/reference/cnetaddressctrl-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)
