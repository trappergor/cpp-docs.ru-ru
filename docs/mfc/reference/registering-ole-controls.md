---
title: "Регистрация элементов управления OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.ole
dev_langs: C++
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b11e943b8aa6427517ecb5b32ddf6f56442f5d0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="registering-ole-controls"></a>Регистрация элементов управления OLE
Элементы управления OLE, подобно другим объектам сервера OLE, может осуществляться других OLE-совместимых приложений. Это достигается путем регистрации библиотеки типов и класс элемента управления.  
  
 Следующие функции позволяют добавлять и удалять элемент управления класса страницы свойств и библиотеки типов в базе данных регистрации Windows:  
  
### <a name="registering-ole-controls"></a>Регистрация элементов управления OLE  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Добавляет класс элемента управления для базы данных регистрации.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Добавляет страницу свойств элемента управления для базы данных регистрации.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Добавляет базу данных регистрации библиотеки типов элемента управления.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Удаляет класс элемента управления или класса страницы свойств из базы данных регистрации.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Удаление библиотеки типов элемента управления из базы данных регистрации.|  
  
 `AfxOleRegisterTypeLib`обычно вызывается в реализации библиотеки DLL элементов управления `DllRegisterServer`. Аналогичным образом `AfxOleUnregisterTypeLib` вызывается `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, и `AfxOleUnregisterClass` обычно вызываются с `UpdateRegistry` функции-члене класса элемента управления класса фабрики или странице свойств.  
  
##  <a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass  
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
 Класс уникальный идентификатор элемента управления.  
  
 `pszProgID`  
 Уникальный идентификатор программы элемента управления.  
  
 `idTypeName`  
 Идентификатор ресурса строки, которая содержит имя пользователя для чтения типа для элемента управления.  
  
 *idBitmap*  
 Идентификатор ресурса точечного рисунка, используемый для представления элемента управления OLE в панели инструментов или палитры.  
  
 `nRegFlags`  
 Содержит один или несколько из следующих флагов:  
  
- `afxRegInsertable`Позволяет элементу управления отображаются в диалоговом окне Вставка объекта OLE-объекты.  
  
- `afxRegApartmentThreading`Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
- `afxRegFreeThreading`Задает модель потоков в реестре, ThreadingModel = Free.  
  
     Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` для задания ThreadingModel = Both. В разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в Windows SDK, Дополнительные сведения о потоковой модели регистрации.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 `int` `nRegFlags` параметр был **BOOL** параметр *bInsertable*, разрешены или запрещены управления вставляемый из диалогового окна Вставить объект поле.  
  
 *dwMiscStatus*  
 Содержит один или несколько из следующих флагов состояния (Описание флагов см. в разделе **OLEMISC, ПОЗВОЛЯЯ** перечисления в Windows SDK):  
  
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
 Ненулевое значение, если класс элемента управления была зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет элементу управления для использования с контейнерами, OLE-элемент управления виду. `AfxOleRegisterControlClass`обновление реестра с именем элемента управления и его расположение в системе, а также задается модель потоков, который поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [Технические заметки 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модели подразделения потоков в OLE элементы управления,» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 В приведенном выше примере показано, как `AfxOleRegisterControlClass` вызывается с помощью флага для вставляемые и флаг для подразделения модели ORed вместе для создания шестого параметра:  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Элемента управления будут отображаться в диалоговом окне Вставка объекта для включенных контейнеров и он будет поддержкой модели подразделения. Подразделения модели элементов управления необходимо убедиться, статический класс данных защищается блокировки, с, чтобы элемент управления в одно подразделение осуществляет доступ к статические данные, он не отключить планировщиком до ее завершения, и запускается другой экземпляр того же класса с помощью те же статические данные. Любой доступ к статическим данным будет заключаться в критический раздел кода.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass  
 Регистрирует класса страницы свойств с регистрационной базы данных Windows.  
  
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
 Класс уникальный идентификатор страницы свойств.  
  
 `idTypeName`  
 Идентификатор ресурса строки, которая содержит имя пользователя для чтения на странице свойств.  
  
 `nRegFlags`  
 Может содержать флаг.  
  
- `afxRegApartmentThreading`Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 `int` `nRegFlags` параметр не доступен. Обратите внимание, что `afxRegInsertable` флаг не является допустимым параметром для страницы свойств и вызовет ASSERT в MFC, если оно задано  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс элемента управления была зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет страницу свойств для использования с контейнерами, OLE-элемент управления виду. `AfxOleRegisterPropertyPageClass`Добавляет в реестр имя страницы свойств и его расположение в системе, а также задается модель потоков, который поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [Технические заметки 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модели подразделения потоков в OLE элементы управления,» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в Windows SDK.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib  
 Регистрирует библиотеку типов с регистрационной базы данных Windows и позволяет библиотеки типов для использования других контейнеров, которые являются OLE-элемент управления виду.  
  
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
 Указывает необязательное имя файла библиотеки типов локализованные (. Файл TLB) для элемента управления.  
  
 *pszHelpDir*  
 Имя каталога, где можно найти файл справки для библиотеки типов. Если **NULL**, файл справки считается в том же каталоге, как у библиотеки типов, сам.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обновляет реестр с имя библиотеки типов и его расположение в системе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>AfxOleUnregisterClass  
 Удаляет класс элемента управления или свойства страниц из базы данных регистрации Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор clsID*  
 Идентификатор уникальный класс элемента управления или свойства страницы.  
  
 `pszProgID`  
 Уникальный идентификатор программы управления или свойства страницы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс элемента управления или свойства страницы была успешно удалена; в противном случае — 0.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib  
 Вызывайте эту функцию, чтобы удалить запись библиотеки типов из регистрационной базы данных Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Параметры  
 `tlID`  
 Уникальный идентификатор библиотеки типов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов была успешно удалена; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
