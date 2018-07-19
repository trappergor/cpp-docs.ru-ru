---
title: Регистрация элементов управления OLE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 468eb677a0073e25c9ef33182aea0d321cded352
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335626"
---
# <a name="registering-ole-controls"></a>Регистрация элементов управления OLE
Элементы управления OLE, как и другие объекты сервера OLE, может осуществляться другими приложениями, поддержкой OLE. Это достигается путем регистрации библиотеки типов и класс элемента управления.  
  
 Следующие функции позволяют добавлять и удалять класса элемента управления, страницы свойств и библиотеки типов в базе данных регистрации Windows:  
  
### <a name="registering-ole-controls"></a>Регистрация элементов управления OLE  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Добавляет класс элемента управления к базе данных регистрации.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Добавляет страницу свойств элемента управления к базе данных регистрации.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Добавляет базу данных регистрации библиотеки типов элемента управления.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Удаляет из базы данных регистрации класса элемента управления или класса страницы свойств.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Удаляет библиотеки типов элемента управления из базы данных регистрации.|  
  
 `AfxOleRegisterTypeLib` обычно вызывается в реализации библиотеки DLL элементов управления `DllRegisterServer`. Аналогичным образом `AfxOleUnregisterTypeLib` вызывается `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, и `AfxOleUnregisterClass` , обычно вызываются `UpdateRegistry` функции-члене класса элемента управления класса фабрики или странице свойств.  
  
##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass  
 Регистрирует класс элемента управления с базой данных регистрации Windows.  
  
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
 *hInstance*  
 Дескриптор экземпляра модуля, связанный с классом элемента управления.  
  
 *CLSID*  
 Класс уникальный идентификатор элемента управления.  
  
 *pszProgID*  
 Уникальный идентификатор программы элемента управления.  
  
 *idTypeName*  
 Идентификатор ресурса строки, который содержит имя пользователя для чтения типа для элемента управления.  
  
 *idBitmap*  
 Идентификатор ресурса растрового изображения, используемый для представления элемента управления OLE в панели инструментов или палитры.  
  
 *nRegFlags*  
 Содержит один или несколько из следующих флагов:  
  
- `afxRegInsertable` Позволяет элементу управления отображаются в диалоговом окне Вставка объекта для объектов OLE.  
  
- `afxRegApartmentThreading` Задает модель потоков в реестре ThreadingModel = подразделения.  
  
- `afxRegFreeThreading` Задает модель потоков в реестре ThreadingModel = Free.  
  
     Вы можете объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` присвоить ThreadingModel = Both. См. в разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в пакете SDK для Windows, Дополнительные сведения по использованию потоков регистрации модели.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 **int** *nRegFlags* параметр был параметром BOOL *bInsertable*, разрешены или запрещены элемент управления, который будет вставлен из инструкции Insert Объект-диалоговое окно.  
  
 *dwMiscStatus*  
 Содержит один или несколько из следующих флагов состояния (Описание флагов, перечислении OLEMISC см. в пакете SDK для Windows):  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   УСТАНОВКЕ OLEMISC_INSIDEOUT  
  
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
  
 *wVerMajor*  
 Основной номер версии класса элемента управления.  
  
 *wVerMinor*  
 Дополнительный номер версии класса элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс элемента управления был зарегистрирован; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет элементу управления для использования с контейнерами, учитывать OLE-control. `AfxOleRegisterControlClass` обновление реестра с именем элемента управления и его расположение в системе и также задает потоковую модель, которая поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [технические 64 Примечание](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модель с подразделением потоков в OLE элементы управления» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 В приведенном выше примере показано, как `AfxOleRegisterControlClass` вызывается с флагом для пригодным для вставки и флаг для подразделения модели ORed друг с другом, чтобы создать шестого параметра:  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Элемент управления будет отображаться в диалоговом окне Вставка объекта для включенных контейнеров, и будет модели с поддержкой. Элементы управления с поддержкой модели подразделения необходимо убедиться, статический класс, который данные защищены блокировок, таким образом, чтобы элемент управления в одно подразделение обращается к статические данные, он не отключить планировщик до ее завершения, и другой экземпляр того же класса, запускается с помощью те же статические данные. Любой доступ к статическим данным будет заключаться в критический раздел кода.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Регистрирует класс страницы свойств с базой данных регистрации Windows.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Параметры  
 *hInstance*  
 Дескриптор экземпляра модуля, связанный с классом страницы свойств.  
  
 *CLSID*  
 Идентификатор уникального класса страницы свойств.  
  
 *idTypeName*  
 Идентификатор ресурса строки, который содержит понятное пользователю имя страницы свойств.  
  
 *nRegFlags*  
 Может содержать флаг:  
  
- `afxRegApartmentThreading` Задает модель потоков в реестре ThreadingModel = подразделения.  
  
> [!NOTE]
>  В версиях MFC до MFC 4.2 **int** *nRegFlags* параметр был недоступен. Обратите внимание, что `afxRegInsertable` флаг не является допустимым параметром для страницы свойств и вызовет УТВЕРЖДЕНИЕ в MFC, если задано значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс элемента управления был зарегистрирован; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет странице свойств для использования с контейнерами, учитывать OLE-control. `AfxOleRegisterPropertyPageClass` Добавляет в реестр имя страницы свойств и его расположение в системе, а также задает потоковую модель, которая поддерживает элемент управления в реестре. Дополнительные сведения см. в разделе [технические 64 Примечание](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), «Модель с подразделением потоков в OLE элементы управления» и [о процессах и потоках](http://msdn.microsoft.com/library/windows/desktop/ms681917) в пакете Windows SDK.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Регистрирует библиотеку типов в базе данных регистрации Windows и позволяет библиотеку типов для использования других контейнеров, которые являются виду OLE-control.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 *hInstance*  
 Дескриптор экземпляра приложения, связанного с библиотекой типов.  
  
 *tlid*  
 Уникальный идентификатор библиотеки типов.  
  
 *pszFileName*  
 Указывает необязательное имя файла библиотеки типов локализованные (. Файл TLB) для элемента управления.  
  
 *pszHelpDir*  
 Имя каталога, где можно найти файл справки для библиотеки типов. Если значение равно NULL, предполагается, что в файле справки в том же каталоге, что и библиотека типов, сам.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов была зарегистрирована; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция добавляет в реестр имя библиотеки типов и его расположение в системе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Удаляет класс элемента управления или свойства страниц из базы данных регистрации Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Параметры  
 *clsID*  
 Идентификатор уникального класса страницы элемента управления или свойства.  
  
 *pszProgID*  
 Уникальный идентификатор программы страницы элемента управления или свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления или свойства класса page была успешно удалена; в противном случае 0.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Вызывайте эту функцию, чтобы удалить запись библиотеки типов из базы данных регистрации Windows.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Параметры  
 *tlID*  
 Уникальный идентификатор библиотеки типов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если библиотека типов была успешно удалена; в противном случае 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
