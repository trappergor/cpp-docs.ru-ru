---
title: "Класс IProvideClassInfo2Impl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0d3bed0f625e396b63ada19ded02ba9ad3b697b0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iprovideclassinfo2impl-class"></a>Класс IProvideClassInfo2Impl
Этот класс предоставляет реализацию по умолчанию [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) и [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) методы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>Параметры  
 *pcoclsid*  
 Указатель на идентификатор компонентного класса.  
  
 *psrcid*  
 Указатель на идентификатор по умолчанию класс coclass исходящий disp-интерфейса.  
  
 `plibid`  
 Указатель на идентификатор LIBID библиотеки типов, содержащий сведения об интерфейсе. По умолчанию передается библиотеки типов на уровне сервера.  
  
 `wMajor`  
 Основной номер версии библиотеки типов. Значение по умолчанию — 1.  
  
 `wMinor`  
 Дополнительный номер версии библиотеки типов. Значение по умолчанию — 0.  
  
 `tihclass`  
 Класс, используемый для управления данными типа компонентного класса. Значение по умолчанию — `CComTypeInfoHolder`.  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Извлекает **ITypeInfo** указатель на класс coclass сведения о типе.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Извлекает идентификатор GUID объекта исходящих disp-интерфейса.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Управляет сведения о типе для компонентного класса.|  
  
## <a name="remarks"></a>Примечания  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) расширяет интерфейс [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) , добавив `GetGUID` метод. Этот метод позволяет клиенту получить объект исходящего интерфейса IID набор событий по умолчанию. Класс `IProvideClassInfo2Impl` предоставляет реализацию по умолчанию **IProvideClassInfo** и `IProvideClassInfo2` методы.  
  
 `IProvideClassInfo2Impl`содержит статический член типа `CComTypeInfoHolder` , управляющий сведения о типе для компонентного класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 Извлекает `ITypeInfo` указатель на класс coclass сведения о типе.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 Извлекает идентификатор GUID объекта исходящих disp-интерфейса.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Конструктор.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы `AddRef` на [_tih](#_tih) член. Вызывает деструктор **версии**.  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 Статические данные-член является экземпляром класса параметр шаблона класса `tihclass`, который по умолчанию является `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Примечания  
 `_tih`Управляет сведения о типе для компонентного класса.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

