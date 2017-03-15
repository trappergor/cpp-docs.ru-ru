---
title: "Регистрация элементов управления OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls, registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9c54fb7dc3802e78c8dc68df02ff55ef4732a36b
ms.lasthandoff: 02/24/2017

---
# <a name="registering-ole-controls"></a>Регистрация элементов управления OLE
Элементы управления OLE, подобно другим объектам сервера OLE, может осуществляться других OLE-совместимых приложений. Это достигается путем регистрации библиотеки типов и класса элемента управления.  
  
 Следующие функции позволяют добавлять и удалять класса элемента управления, страницы свойств и библиотеки типов в базе данных регистрации Windows:  
  
### <a name="registering-ole-controls"></a>Регистрация элементов управления OLE  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Добавляет класс элемента управления базой данных регистрации.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Добавляет страницы свойств для управления базой данных регистрации.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Добавляет базу данных регистрации библиотеки типов элемента управления.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Удаляет из базы данных регистрации класса элемента управления или класса страницы свойств.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Удаляет библиотеку типов элемента управления из базы данных регистрации.|  
  
 `AfxOleRegisterTypeLib`обычно вызывается в реализации библиотеки DLL элементов управления `DllRegisterServer`. Аналогичным образом `AfxOleUnregisterTypeLib` вызывается `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, и `AfxOleUnregisterClass` , обычно вызываются `UpdateRegistry` функции-члены элемента управления класса фабрики или страницы свойств.  
  
##  <a name="a-nameafxoleregistercontrolclassa--afxoleregistercontrolclass"></a><a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass  
 Регистрирует класс элемента управления с регистрационной базы данных Windows.  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра модуля, связанный с классом элемента управления.  
  
 `clsid`  
 Идентификатор уникального класса элемента управления.  
  
 `pszProgID`  
 Уникальный идентификатор программы элемента управления.  
  
 `idTypeName`  
 Идентификатор ресурса строки, который содержит имя пользователя для чтения типа для элемента управления.  
  
 *idBitmap*  
 Идентификатор ресурса растрового изображения, используемый для представления элемента управления OLE в панели инструментов или палитре.  
  
 `nRegFlags`  
 Содержит один или несколько из следующих флагов:  
  
- `afxRegInsertable`Позволяет элементу управления отображаются в диалоговом окне Вставка объекта OLE-объекты.  
  
- `afxRegApartmentThreading`Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
- `afxRegFreeThreading`Задает модель потоков в реестре, ThreadingModel = Free.  
  
     Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` для задания ThreadingModel = Both. В разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о потоковой модели регистрации.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 `int` `nRegFlags` параметр **BOOL** параметр *bInsertable*, разрешены или запрещены для вставки в диалоговом окне Вставка объекта элемента управления.  
  
 *dwMiscStatus*  
 Содержит один или несколько из следующих флагов состояния (Описание флагов см. в разделе **OLEMISC, ПОЗВОЛЯЯ** перечисления в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]):  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   OLEMISC_ACTIVATEWHENVISIBLE  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 Уникальный идентификатор класса элемента управления.  
  
 `wVerMajor`  
 Основной номер версии класса элемента управления.  
  
 `wVerMinor`  
 Дополнительный номер версии класса элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если был зарегистрирован класс элемента управления; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет элементу управления для использования с контейнерами, учитывать OLE-control. `AfxOleRegisterControlClass`обновление реестра с именем элемента управления и его расположение в системе, а также задается потоковой модели, который поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [Технические заметки 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модели потоков в OLE элементы управления» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl&11;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 В примере выше показано, как `AfxOleRegisterControlClass` вызывается с флагом для вставляемые и флаг для подразделения модели оператором вместе для создания шестой параметр:  
  
 [!code-cpp[NVC_MFCAxCtl&#12;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Элемент управления будет отображаться в диалоговом окне Вставка объекта для включенных контейнеров и будет учитывать модели подразделения. Подразделения модели элементов управления необходимо убедиться, статический класс, который данные защищаются блокировки, таким образом, хотя элемент управления в одно подразделение доступ к статических данных, она не отключена планировщик до его завершения, и запускается еще один экземпляр того же класса, с помощью тех же статических данных. Любой доступ к статическим данным будет заключаться в критический раздел кода.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameafxoleregisterpropertypageclassa--afxoleregisterpropertypageclass"></a><a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass  
 Регистрирует класс страницы свойств регистрационной базы данных Windows.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра модуля, связанные с класса страницы свойств.  
  
 `clsid`  
 Идентификатор уникального класса страницы свойств.  
  
 `idTypeName`  
 Идентификатор ресурса строки, который содержит имя пользователя для чтения на странице свойств.  
  
 `nRegFlags`  
 Может содержать флаг:  
  
- `afxRegApartmentThreading`Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 `int` `nRegFlags` параметр не доступен. Обратите внимание, что `afxRegInsertable` флаг не является допустимым параметром для страниц свойств и вызовет ASSERT в MFC, если оно имеет значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если был зарегистрирован класс элемента управления; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет странице свойств для использования с контейнерами, учитывать OLE-control. `AfxOleRegisterPropertyPageClass`обновление реестра с именем страницы свойств и его расположение в системе, а также задается потоковой модели, который поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [Технические заметки 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модели потоков в OLE элементы управления» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameafxoleregistertypeliba--afxoleregistertypelib"></a><a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib  
 Регистрирует библиотеку типов с регистрационной базы данных Windows и позволяет библиотеки типов для использования других контейнеров, учитывать OLE-control.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра приложения, связанного с библиотекой типов.  
  
 *tlid*  
 Уникальный идентификатор библиотеки типов.  
  
 *pszFileName*  
 Указывает необязательный имя файла библиотеки типов локализованного (. Файл TLB) для элемента управления.  
  
 *pszHelpDir*  
 Имя каталога, где можно найти файл справки для библиотеки типов. Если **NULL**, файл справки считается в том же каталоге, как у библиотеки типов, сам.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов была зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция добавляет в реестр имя библиотеки типов и его расположение в системе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation&#7;](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation №&8;](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameafxoleunregisterclassa--afxoleunregisterclass"></a><a name="afxoleunregisterclass"></a>AfxOleUnregisterClass  
 Удаляет класс элемента управления или свойства страниц из базы данных регистрации Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Параметры  
 *clsID*  
 Идентификатор уникального класса страницы элемента управления или свойства.  
  
 `pszProgID`  
 Уникальный идентификатор программы страницы элемента управления или свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс элемента управления или свойства страницы была успешно удалена; в противном случае — 0.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameafxoleunregistertypeliba--afxoleunregistertypelib"></a><a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib  
 Эта функция вызывается для удаления записи типа библиотеки из регистрационной базы данных Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Параметры  
 `tlID`  
 Уникальный идентификатор библиотеки типов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов была успешно удалена; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl&#13;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

