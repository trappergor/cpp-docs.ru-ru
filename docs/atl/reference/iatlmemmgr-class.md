---
title: Класс IAtlMemMgr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d623df9fcab776a42fda7ca13269554b9f38b56c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880577"
---
# <a name="iatlmemmgr-class"></a>Класс IAtlMemMgr
Этот класс представляет интерфейс для диспетчера памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[выделить](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[бесплатно](#free)|Вызовите этот метод для освобождения блока памяти.|  
|[GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти.|  
|[Перераспределение](#reallocate)|Вызовите этот метод для выполняют перераспределение блока памяти.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс реализуется [CComHeap](../../atl/reference/ccomheap-class.md), [CCRTHeap](../../atl/reference/ccrtheap-class.md), [CLocalHeap](../../atl/reference/clocalheap-class.md), [CGlobalHeap](../../atl/reference/cglobalheap-class.md), или [CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Кучи локальные и глобальные функции выполняются медленнее, чем другими функциями управления памятью и не предоставляют меньше возможностей. Таким образом, новые приложения должны использовать [функции кучи](http://msdn.microsoft.com/library/windows/desktop/aa366711). Они доступны в [CWin32Heap](../../atl/reference/cwin32heap-class.md) класса.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlmem.h  
  
##  <a name="allocate"></a>  IAtlMemMgr::Allocate  
 Вызовите этот метод, чтобы выделить блок памяти.  
  
```
void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nBytes*  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [IAtlMemMgr::Free](#free) или [IAtlMemMgr::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.  
  
### <a name="example"></a>Пример  
 Например, см. в разделе [IAtlMemMgr Обзор](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="free"></a>  IAtlMemMgr::Free  
 Вызовите этот метод для освобождения блока памяти.  
  
```
void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для освобождения памяти, полученных [IAtlMemMgr::Allocate](#allocate) или [IAtlMemMgr::Reallocate](#reallocate).  
  
### <a name="example"></a>Пример  
 Например, см. в разделе [IAtlMemMgr Обзор](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="getsize"></a>  IAtlMemMgr::GetSize  
 Вызовите этот метод, чтобы получить размер выделенного блока памяти.  
  
```
size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер блока памяти в байтах.  
  
### <a name="example"></a>Пример  
 Например, см. в разделе [IAtlMemMgr Обзор](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate  
 Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.  
  
```
void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
 *nBytes*  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [IAtlMemMgr::Free](#free) или [IAtlMemMgr::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.  
  
 По существу, этот метод освобождает память, существующих и выделяя новый блок памяти. На самом деле существующую память может быть расширенных или в противном случае повторного использования.  
  
### <a name="example"></a>Пример  
 Например, см. в разделе [IAtlMemMgr Обзор](../../atl/reference/iatlmemmgr-class.md).  
  
##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu  
 `AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowContextMenu*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI  
 `AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowShowUI*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.  
  
##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 `AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>Параметры  
 *pbAllowWindowless*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor  
 `BackColor` Свойство задает цвет фона окружения контейнера.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>Параметры  
 *pclrBackground*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение по умолчанию этого свойства (в зависимости от родительского окна хоста является ли диалоговое окно или нет).  
  
##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault  
 `DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *pbDisplayAsDefault*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.  
  
##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 `DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwDocHostDoubleClickFlags*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT как значение по умолчанию этого свойства.  
  
##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags  
 `DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *pdwDocHostFlags*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER как значение по умолчанию этого свойства.  
  
##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font  
 `Font` Свойство задает шрифт окружения контейнера.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pFont*  
 [out] Адрес `IFontDisp` указатель на интерфейс, используемый для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.  
  
##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor` Свойство задает цвет переднего плана окружения контейнера.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>Параметры  
 *pclrForeground*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует системный цвет окна как значение по умолчанию этого свойства.  
  
##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID  
 `LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>Параметры  
 *plcidLocaleID*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.  
  
 С помощью этого метода можно обнаружить окружения локальный идентификатор, то есть LocaleID программы управления, используется. Зная код языка, можно вызвать код для загрузки заголовков зависящих от языкового стандарта, текст сообщения об ошибке, и так далее из файла ресурсов или вспомогательной библиотеке DLL.  
  
##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect  
 `MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 *pbMessageReflect*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath  
 `OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Параметры  
 *pbstrOptionKeyPath*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles  
 `ShowGrabHandles` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам с маркерами захвата.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>Параметры  
 *pbShowGrabHandles*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 ATL узла объекта реализация всегда возвращает значение VARIANT_FALSE в качестве значения этого свойства.  
  
##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching  
 `ShowHatching` Внешнее свойство позволяет элементу управления узнать, если она должна нарисовать сам hatched.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>Параметры  
 *pbShowHatching*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 ATL узла объекта реализация всегда возвращает значение VARIANT_FALSE в качестве значения этого свойства.  
  
##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode  
 `UserMode` Свойство задает режим работы окружения пользователя контейнера.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 *pbUserMode*  
 [out] Адрес переменной для получения текущего значения этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu  
 `AllowContextMenu` Свойство указывает, разрешено ли размещенный элемент управления для отображения свое собственное контекстное меню.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowContextMenu*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI  
 `AllowShowUI` Свойство указывает, разрешено ли размещенный элемент управления отображать пользовательский интерфейс.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowShowUI*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.  
  
##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 `AllowWindowlessActivation` Свойство указывает, будет ли контейнер давать возможность активации без окна.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>Параметры  
 *bAllowWindowless*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor  
 `BackColor` Свойство задает цвет фона окружения контейнера.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>Параметры  
 *clrBackground*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует COLOR_BTNFACE или COLOR_WINDOW как значение по умолчанию этого свойства (в зависимости от родительского окна хоста является ли диалоговое окно или нет).  
  
##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault  
 `DisplayAsDefault` является свойством окружения, который позволяет элементу управления проверить, является ли элемент управления по умолчанию.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *bDisplayAsDefault*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_FALSE как значение по умолчанию этого свойства.  
  
##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 `DocHostDoubleClickFlags` Свойство определяет операцию, которая должна быть выполнена в соответствии с двойным щелчком.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDocHostDoubleClickFlags*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует DOCHOSTUIDBLCLK_DEFAULT как значение по умолчанию этого свойства.  
  
##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags  
 `DocHostFlags` Свойство указывает возможностями интерфейса пользователя объекта узла.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDocHostFlags*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует DOCHOSTUIFLAG_NO3DBORDER как значение по умолчанию этого свойства.  
  
##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font  
 `Font` Свойство задает шрифт окружения контейнера.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pFont*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует шрифт графического пользовательского интерфейса по умолчанию или системный шрифт как значение по умолчанию этого свойства.  
  
##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor` Свойство задает цвет переднего плана окружения контейнера.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>Параметры  
 *clrForeground*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует системный цвет окна как значение по умолчанию этого свойства.  
  
##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID  
 `LocaleID` Свойство задает идентификатор внешней языковой стандарт контейнера.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>Параметры  
 *lcidLocaleID*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует языковой стандарт пользователя по умолчанию как значение по умолчанию этого свойства.  
  
##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect  
 `MessageReflect` Внешнее свойство указывает, отражает ли контейнер сообщений для размещенного элемента управления.  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 *bMessageReflect*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath  
 `OptionKeyPath` Свойство указывает путь к разделу реестра для параметров пользователя.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrOptionKeyPath*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode  
 `UserMode` Свойство задает режим работы окружения пользователя контейнера.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 *bUserMode*  
 [in] Новое значение этого свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Реализация объекта узла ATL использует значение VARIANT_TRUE как значение по умолчанию этого свойства.  
  
##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Этот метод вызывается в дополнение к интерфейс внешнее свойство по умолчанию с помощью определенного пользователем интерфейса.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 *pDispatch*  
 Указатель на новый интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Когда `SetAmbientDispatch` вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любого свойства или методы, задаваемые для размещенным элементом управления, если эти свойства еще не заданы [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl  
 Прикрепляет элемент существующего (и предварительно инициализированных) в объект узла, с помощью окна определяется *hWnd*.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkControl*  
 [in] Указатель на `IUnknown` интерфейса элемента управления должны быть присоединены к объекта узла.  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl  
 Создает элемент управления, инициализирует его и размещает его в окне, идентифицируемый *hWnd*.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>Параметры  
 *lpTricsData*  
 [in] Строка, определяющая элемент управления для создания. Может быть (необходимо использовать фигурные скобки) CLSID, ProgID, URL-адрес или необработанное HTML (с префиксом **MSHTML:**).  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
 *pStream*  
 [in] Указатель на интерфейс для поток, содержащий данные инициализации для элемента управления. Может иметь значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Это окно будет разделяться на подклассы объектом узла, предоставляя этот интерфейс, чтобы сообщения могут быть отражены в элемент управления и другие функции контейнеров будут работать.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).  
  
 Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex).  
  
##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx  
 Создает элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *lpTricsData*  
 [in] Строка, определяющая элемент управления для создания. Может быть (необходимо использовать фигурные скобки) CLSID, ProgID, URL-адрес или необработанное HTML (с префиксом **MSHTML:**).  
  
 *hWnd*  
 [in] Дескриптор окна, используемый для размещения.  
  
 *pStream*  
 [in] Указатель на интерфейс для поток, содержащий данные инициализации для элемента управления. Может иметь значение NULL.  
  
 *ppUnk*  
 [out] Адрес указателя, который будет получать `IUnknown` интерфейса созданный элемент управления. Может иметь значение NULL.  
  
 *riidAdvise*  
 [in] Идентификатор исходящего интерфейса на содержащийся объект. Может быть IID_NULL.  
  
 *punkAdvise*  
 [in] Указатель на `IUnknown` интерфейс приемника объекта должен быть подключен к точкой соединения в автономной объекта, заданного параметром `iidSink`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 В отличие от `CreateControl` метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданный элемент управления и настройка приемник событий для получения события, инициируемые элементом управления.  
  
 Чтобы создать лицензированный элемент управления ActiveX, см. в разделе [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex).  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 Возвращает заданный указатель интерфейса, предоставляемые размещенного элемента управления.  
  
```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 [in] Идентификатор интерфейса для запрашиваемого элемента управления.  
  
 *ppvObject*  
 [out] Адрес указателя, который получит указанный интерфейс созданный элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 Задает внешний disp-интерфейс, который доступен на вложенные элементы управления через [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 *pDisp*  
 [in] Указатель на `IDispatch` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
 Вызывайте эту функцию, чтобы задать внешний [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>Параметры  
 *pDisp*  
 [in] Указатель на `IDocHostUIHandlerDispatch` интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется элементами управления (например, элемент управления браузера), отправляющие запросы к узлу для `IDocHostUIHandlerDispatch` интерфейс.  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
 Создает лицензированный элемент управления, инициализирует его и размещает его в окне, идентифицируемый `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrLic*  
 [in] BSTR, содержащий лицензионный ключ для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IAxWinHostWindow::CreateControl](#createcontrol) описание оставшихся параметров и возвращаемого значения.  
  
 Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Пример  
 См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
 Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [IAxWinHostWindow::CreateControl](#createcontrol).  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrLic*  
 [in] BSTR, содержащий лицензионный ключ для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IAxWinHostWindow::CreateControlEx](#createcontrolex) описание оставшихся параметров и возвращаемого значения.  
  
### <a name="example"></a>Пример  
 См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLicEx`.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
