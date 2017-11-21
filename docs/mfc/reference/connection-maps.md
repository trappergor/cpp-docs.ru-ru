---
title: "Схемы подключения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.maps
dev_langs: C++
helpviewer_keywords: connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3084bd69293b9419369f2457695965481d3dec3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="connection-maps"></a>Схемы подключения
Элементы управления OLE, могут предоставлять интерфейсы другим приложениям. Эти интерфейсы только разрешить доступ из контейнера в этот элемент управления. Если элемента управления OLE хочет получить доступ к внешних интерфейсов другими объектами OLE, необходимо установить точку подключения. Эта точка соединения позволяет контролировать исходящий доступ к внешней подготовки к отправке карт, таких как схемы событий или функции уведомления.  
  
 Библиотеки классов Microsoft Foundation предоставляет модель программирования, которая поддерживает точки подключения. В этой модели «подключение сопоставляет» используются для обозначения интерфейсы или точки подключения для элемента управления OLE. Схемы подключения содержат один макрос для каждой точки подключения. Дополнительные сведения о схемы подключения см. в разделе [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) класса.  
  
 Как правило, элемент управления будет поддерживать только двумя точками соединения: для события и уведомления о свойств. Они реализуются `COleControl` базового класса и требуют дополнительных действий разработчиком элемента управления. Всем точкам дополнительное подключение, необходимо реализовать в классе необходимо добавить вручную. Для поддержки схемы подключения и точки, MFC предоставляет следующие макросы:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Подключение карты объявление и определение границ  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Объявляет внедренный класс, реализующий дополнительных подключений, (следует использовать в объявлении класса).|  
|[END_CONNECTION_PART](#end_connection_part)|Завершает объявления точки подключения (следует использовать в объявлении класса).|  
|[CONNECTION_IID](#connection_iid)|Указывает идентификатор интерфейса точки подключения для элемента управления.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Объявляет, что сопоставление подключения будет использоваться в классе (следует использовать в объявлении класса).|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Начинается определение сопоставления подключения (следует использовать в реализацию класса).|  
|[END_CONNECTION_MAP](#end_connection_map)|Завершает определение сопоставления подключения (следует использовать в реализацию класса).|  
|[CONNECTION_PART](#connection_part)|Указывает точку подключения в сопоставление элемента управления подключения.|  
  
 Следующие функции помочь приемник в установке и разрыве подключения с помощью точек подключения.  
  
### <a name="initializationtermination-of-connection-points"></a>Инициализация и прекращение точек подключения  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Устанавливает соединение между источником и приемником.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Разрывает соединение между источником и приемником.|  
  
##  <a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 Используйте `BEGIN_CONNECTION_PART` макрос, чтобы начать определение дополнительного соединения точек за точки подключения уведомления события и свойства.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, точка подключения которого это.  
  
 *localClass*  
 Задает имя локального класса, который реализует точку подключения.  
  
### <a name="remarks"></a>Примечания  
 В файле объявления (.h), который определяет функции-члены класса, запустите точки подключения с `BEGIN_CONNECTION_PART` макрос, затем добавьте `CONNECTION_IID` макрос и любые другие функции-члены необходимо реализовать и выполнить сопоставление точки подключения с `END_CONNECTION_PART` макрос.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="end_connection_part"></a>END_CONNECTION_PART  
 Завершает объявления точки подключения.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 *localClass*  
 Задает имя локального класса, который реализует точку подключения.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="connection_iid"></a>CONNECTION_IID  
 Используйте между `BEGIN_CONNECTION_PART` и `END_CONNECTION_PART` макросы, чтобы определить идентификатор интерфейса для точки подключения, поддерживаемые элементом управления OLE.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 Идентификатор интерфейса интерфейса, называется точкой подключения.  
  
### <a name="remarks"></a>Примечания  
 `iid` Аргумент — это интерфейс, идентификатор, используемый для определения интерфейса, который будет вызывать точки подключения на его подключенных приемники. Пример:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 Указывает точку подключения, которая вызывает `ISinkInterface` интерфейса.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 Каждый `COleControl`-производный класс в программе можно указать сопоставление подключения для указания точки дополнительного соединения, которые поддерживает элемент управления.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления поддерживает дополнительные точки, используйте `DECLARE_CONNECTION_MAP` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_CONNECTION_MAP` макрос, `CONNECTION_PART` макросы для каждой точки соединения элемента управления и `END_CONNECTION_MAP` макрос для объявления конец карты подключений.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 Каждый `COleControl`-производный класс в программе может предоставить сопоставление подключения для указания точки подключения, которые будут поддерживать элемент управления.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, сопоставления которых подключение.  
  
 *theBase*  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В реализации (. Файл CPP), который определяет функции-члены класса, запустить сопоставление подключения с `BEGIN_CONNECTION_MAP` макрос, затем добавить макрос записи для каждой из точек соединения с помощью [CONNECTION_PART](#connection_part) макрос. И, наконец, завершите подключение карты с [END_CONNECTION_MAP](#end_connection_map) макрос.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="end_connection_map"></a>END_CONNECTION_MAP  
 Завершает определение карте соединения.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="connection_part"></a>CONNECTION_PART  
 Сопоставляет точку подключения для элемента управления OLE с идентификатором определенный интерфейс.  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, точка подключения которого это.  
  
 `iid`  
 Идентификатор интерфейса интерфейса, называется точкой подключения.  
  
 *localClass*  
 Задает имя локального класса, который реализует точку подключения.  
  
### <a name="remarks"></a>Примечания  
 Пример:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 реализует карту соединения с точкой подключения, которая вызывает `IID_ISinkInterface` интерфейса.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 Эта функция вызывается для установления соединения между исходным, определяемое `pUnkSrc`и приемником, определяемое `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkSrc`  
 Указатель на объект, который вызывает интерфейс.  
  
 `pUnkSink`  
 Указатель на объект, реализующий интерфейс.  
  
 `iid`  
 Идентификатор интерфейса подключения.  
  
 `bRefCount`  
 **Значение TRUE,** указывает, для создания соединения приводит количество ссылок на `pUnkSink` увеличивается. **FALSE** указывает счетчик ссылок не увеличивается.  
  
 `pdwCookie`  
 Указатель на `DWORD` где возвращается идентификатор подключения. Это значение должно передаваться как `dwCookie` параметра `AfxConnectionUnadvise` при разрыве подключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подключение установлено; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 Вызывайте эту функцию, чтобы разорвать подключение между исходным, определяемое `pUnkSrc`и приемником, определяемое `pUnkSink`.  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkSrc`  
 Указатель на объект, который вызывает интерфейс.  
  
 `pUnkSink`  
 Указатель на объект, реализующий интерфейс.  
  
 `iid`  
 ИД интерфейса точки подключения интерфейса.  
  
 `bRefCount`  
 **Значение TRUE,** указывает, разрыв соединения приводит количество ссылок на `pUnkSink` уменьшается. **FALSE** указывает, что счетчик ссылок не быть уменьшается на единицу.  
  
 `dwCookie`  
 Идентификатор соединения, возвращенных `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подключение было отключено; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
