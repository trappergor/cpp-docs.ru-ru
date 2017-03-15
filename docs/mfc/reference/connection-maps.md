---
title: "Схемы подключения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
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
ms.openlocfilehash: 8947930d20cc65075abe442b233e4c086f10f76e
ms.lasthandoff: 02/24/2017

---
# <a name="connection-maps"></a>Схемы подключения
Элементы управления OLE, могут предоставлять интерфейсы для других приложений. Эти интерфейсы только разрешить доступ из контейнера в этот элемент управления. Если элемента управления OLE хочет получить доступ к внешних интерфейсов другими объектами OLE, необходимо установить точку подключения. Эта точка соединения позволяет управления исходящий доступ к внешней диспетчеризации карт, таких как схемы событий или функции уведомления.  
  
 Библиотеки классов Microsoft Foundation предоставляет модель программирования, которая поддерживает точки подключения. В этой модели «подключения сопоставляет» используются для обозначения интерфейсы или точки подключения для элемента управления OLE. Схемы подключения содержат один макрос для каждой точки подключения. Дополнительные сведения о картах подключения в разделе [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) класса.  
  
 Как правило, элемент управления будет поддерживать только двумя точками соединения: для событий и уведомлений свойство. Они реализуются `COleControl` базового класса и требуют дополнительных действий для записи элемента управления. Никаких точек дополнительное подключение, необходимо реализовать в классе необходимо добавить вручную. Для поддержки схемы подключения и точки, MFC предоставляет следующие макросы:  
  
### <a name="connection-map-declaration-and-demarcation"></a>Подключение карты объявление и определение границ  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Объявляет внедренный класс, реализующий дополнительных подключений, (необходимо использовать в объявлении класса).|  
|[END_CONNECTION_PART](#end_connection_part)|Завершает объявление точки подключения (необходимо использовать в объявлении класса).|  
|[CONNECTION_IID](#connection_iid)|Указывает идентификатор интерфейса точки подключения для элемента управления.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Объявляет, что сопоставление подключения будет использоваться в классе (необходимо использовать в объявлении класса).|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Начинается определение сопоставления подключения (необходимо использовать реализацию класса).|  
|[END_CONNECTION_MAP](#end_connection_map)|Завершает определение сопоставления подключения (необходимо использовать реализацию класса).|  
|[CONNECTION_PART](#connection_part)|Задает точку подключения в сопоставление элемента управления подключения.|  
  
 Следующие функции помочь приемник в установке и разрыве подключения с использованием точки подключения.  
  
### <a name="initializationtermination-of-connection-points"></a>Инициализация и прекращение точек подключения  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|Устанавливает соединение между источником и приемником.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Разрывает соединение между источником и приемником.|  
  
##  <a name="a-namebeginconnectionparta--beginconnectionpart"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 Используйте `BEGIN_CONNECTION_PART` макрос, чтобы начать определение дополнительного соединения точек за точки подключения уведомления события и свойства.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, точка подключения которого это.  
  
 *localClass*  
 Задает имя локального класса, реализующего точки подключения.  
  
### <a name="remarks"></a>Примечания  
 В файле объявления (.h), который определяет функции-члены класса, начальная точка соединения с `BEGIN_CONNECTION_PART` макрос, затем добавьте `CONNECTION_IID` макрос и любые другие функции-члены необходимо реализовать и выполнить сопоставление точки подключения с `END_CONNECTION_PART` макрос.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameendconnectionparta--endconnectionpart"></a><a name="end_connection_part"></a>END_CONNECTION_PART  
 Завершает объявление точки подключения.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 *localClass*  
 Задает имя локального класса, реализующего точки подключения.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameconnectioniida--connectioniid"></a><a name="connection_iid"></a>CONNECTION_IID  
 Используйте между `BEGIN_CONNECTION_PART` и `END_CONNECTION_PART` макросы, чтобы определить идентификатор интерфейса для точки подключения, поддерживаемые элементом управления OLE.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 Идентификатор интерфейса интерфейса называется точкой подключения.  
  
### <a name="remarks"></a>Примечания  
 `iid` Аргумент — это интерфейс, идентификатор интерфейса, на его подключенных приемники вызовет точки подключения. Например:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#10;](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 Задает точку подключения, которая вызывает `ISinkInterface` интерфейса.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-namedeclareconnectionmapa--declareconnectionmap"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 Каждый `COleControl`-производный класс в программе можно предоставить сопоставление подключения для указания дополнительное подключение точек, которые поддерживает элемент управления.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления поддерживает дополнительные точки, используйте `DECLARE_CONNECTION_MAP` макрос в конце объявления класса. В CPP-файле, который определяет функции-члены класса, используйте `BEGIN_CONNECTION_MAP` макрос, `CONNECTION_PART` макросы для каждой точки соединения элемента управления и `END_CONNECTION_MAP` макрос для объявления конец сопоставление подключения.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-namebeginconnectionmapa--beginconnectionmap"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 Каждый `COleControl`-производный класс в программе может предоставить сопоставление подключения для указания точки подключения, элемент управления будет поддерживать.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, сопоставления которых подключение.  
  
 *theBase*  
 Указывает имя базового класса `theClass`.  
  
### <a name="remarks"></a>Примечания  
 В реализации (. Запустите файл CPP), который определяет функции-члены класса, соединений сопоставлены с `BEGIN_CONNECTION_MAP` макрос, добавьте макрос записи для каждой из точек подключения с помощью [CONNECTION_PART](#connection_part) макрос. И, наконец, завершите соединений сопоставлены с [END_CONNECTION_MAP](#end_connection_map) макрос.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameendconnectionmapa--endconnectionmap"></a><a name="end_connection_map"></a>END_CONNECTION_MAP  
 Завершает определение карту подключения.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameconnectionparta--connectionpart"></a><a name="connection_part"></a>CONNECTION_PART  
 Сопоставляет точку подключения для элемента управления OLE с идентификатором определенного интерфейса.  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 Указывает, что имя класса элемента управления, точка подключения которого это.  
  
 `iid`  
 Идентификатор интерфейса интерфейса называется точкой подключения.  
  
 *localClass*  
 Задает имя локального класса, реализующего точки подключения.  
  
### <a name="remarks"></a>Примечания  
 Например:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 реализует соединений сопоставлены с точки подключения, который вызывает `IID_ISinkInterface` интерфейса.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdisp.h  
  
##  <a name="a-nameafxconnectionadvisea--afxconnectionadvise"></a><a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 Эта функция вызывается для установления соединения между источника, указанного `pUnkSrc`и приемника, определяемое `pUnkSink`.  
  
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
 **Значение TRUE,** указывает, что создание соединения приводит счетчик ссылок `pUnkSink` увеличивается. **FALSE** указывает счетчик не увеличивается.  
  
 `pdwCookie`  
 Указатель на `DWORD` где возвращается идентификатор подключения. Это значение должно передаваться в качестве `dwCookie` параметра `AfxConnectionUnadvise` при разрыве подключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подключение установлено; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints №&8;](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h 

##  <a name="a-nameafxconnectionunadvisea--afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 Вызывайте эту функцию, чтобы разорвать подключение между источником, определяемое `pUnkSrc`и приемника, определяемое `pUnkSink`.  
  
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
 Идентификатор интерфейса интерфейса точки подключения.  
  
 `bRefCount`  
 **Значение TRUE,** указывает, что разрыв соединения приводит счетчик ссылок `pUnkSink` уменьшается. **FALSE** указывает, что счетчик ссылок не должен быть уменьшается на единицу.  
  
 `dwCookie`  
 Идентификатор соединения, возвращаемый `AfxConnectionAdvise`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если подключение было разорвано; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints №&9;](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

