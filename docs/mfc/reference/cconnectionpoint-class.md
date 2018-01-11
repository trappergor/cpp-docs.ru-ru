---
title: "Класс CConnectionPoint | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
dev_langs: C++
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6a9e9fafc2bbee9959a939815a92c9bc63a650f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cconnectionpoint-class"></a>Класс CConnectionPoint
Определяет особый тип интерфейса, используемый для взаимодействия с другими объектами OLE и называемый "точкой подключения".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Создает объект `CConnectionPoint`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](#getconnections)|Возвращает все точки подключения на карте соединения.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Возвращает контейнер элемента управления, которому принадлежит сопоставление подключения.|  
|[CConnectionPoint::GetIID](#getiid)|Извлекает идентификатор интерфейса точки подключения.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Возвращает максимальное число точек соединения, поддерживаемых элементом управления.|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Извлекает указатель на элемент подключения в `pos`.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextConnection` вызова.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Вызывается платформой при установке или разрыва соединения.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Извлекает указатель на интерфейс запрошенного приемника.|  
  
## <a name="remarks"></a>Примечания  
 В отличие от обычных интерфейсов OLE, которые используются для реализации и предоставлять функции элемента управления OLE, точки подключения реализует исходящий интерфейс, который способен инициации действий на другие объекты, например, срабатывание события и уведомления об изменениях.  
  
 Соединение состоит из двух частей: объект, вызывающий интерфейс, называемый «источник» и объект, реализующий интерфейс, называется «приемник». Путем предоставления доступа к точке соединения, источник позволяет приемники для установления соединений к самому себе. Через механизм точек подключения исходный объект получает указатель на реализацию приемника набора функций-членов. Например срабатывание события, реализуемого в приемник, источник может вызовите соответствующий метод реализации приемника.  
  
 По умолчанию `COleControl`-производный класс реализует двумя точками соединения: для событий и для свойства уведомления об изменениях. Эти соединения служат, соответственно, для запуска событий и для уведомления стока (например, контейнер элемента управления) при изменении значения свойства. Также поддерживается для элементов управления OLE для реализации точек подключения дополнительных. Для каждой точки дополнительное подключение, реализованные в классе элемента управления необходимо объявить «подключения часть», реализующий точки подключения. Если вы реализуете одну или несколько точек подключения, необходимо также объявить один «сопоставление подключения» в классе элемента управления.  
  
 В следующем примере показано простое соединение карты и одну точку подключения для `Sample` элемента управления OLE, состоящий из двух фрагментов кода: первая часть объявляет сопоставление подключения и точки; второй реализует этой карты и точки. Первый фрагмент вставляется в объявление класса элемента управления, в разделе `protected` раздела:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 `BEGIN_CONNECTION_PART` И `END_CONNECTION_PART` макросы объявить класс внедренных `XSampleConnPt` (производный от `CConnectionPoint`), реализующий эту точку определенного соединения. Если вы хотите изменить любой `CConnectionPoint` функций-членов или добавить собственные функции-члены, объявите их между этих двух макросов. Например `CONNECTION_IID` переопределяет макрос `CConnectionPoint::GetIID` функция-член, помещенный между этих двух макросов.  
  
 Второй фрагмент кода будет вставлен в файл реализации (. CPP) класса элемента управления. Этот код реализует карты подключения, которая содержит точку дополнительные подключения, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 После вставки этих фрагментов кода образца OLE элемент управления предоставляет точку подключения для **ISampleSink** интерфейса.  
  
 Как правило точки подключения поддерживает «рассылка», — это способность вещание несколько приемников, которые подключены к тот же интерфейс. В следующем фрагменте кода показано, как выполнить многоадресной рассылки путем прохода каждый приемник в точке соединения:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 В этом примере извлекается текущий набор подключений на `SampleConnPt` точки подключения с помощью вызова `CConnectionPoint::GetConnections`. Метод обходит подключений и вызывает `ISampleSink::SinkFunc` для каждого активного подключения.  
  
 Дополнительные сведения об использовании `CConnectionPoint`, см. в статье [точки подключения](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint  
 Создает объект `CConnectionPoint`.  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>CConnectionPoint::GetConnections  
 Эта функция вызывается для получения всех активных соединений для точки подключения.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на массив активных подключений (приемники). Некоторые из указателей в массиве может иметь значение NULL. Каждого НЕНУЛЕВОЙ указатель в этом массиве можно безопасно преобразовать в указатель на интерфейс приемника с помощью оператора приведения.  
  
##  <a name="getcontainer"></a>CConnectionPoint::GetContainer  
 Вызывается платформой для извлечения **IConnectionPointContainer** для точки подключения.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения указателя в контейнер; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно реализуют `BEGIN_CONNECTION_PART` макрос.  
  
##  <a name="getiid"></a>CConnectionPoint::GetIID  
 Вызывается платформой для получения идентификатора интерфейса точки подключения.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на идентификатор интерфейса точки подключения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для возвращения идентификатора интерфейса для этой точки подключения.  
  
##  <a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections  
 Вызывается платформой для извлечения максимальное количество соединений, поддерживаемого точкой подключения.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное количество соединений, поддерживаемые элемент управления, или значение -1, если нет ограничений.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает значение -1, указывающее, не ограничено.  
  
 Переопределите эту функцию, если вы хотите ограничить число приемников, которые могут подключаться к элементу управления.  
  
##  <a name="getnextconnection"></a>CConnectionPoint::GetNextConnection  
 Извлекает указатель на элемент подключения в `pos`.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Указывает ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNextConnection` или [GetStartPosition](#getstartposition) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент соединение с заданным `pos`, или значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в сопоставление подключения. Во время итерации, пропустите все значения NULL, возвращаемых этой функцией.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан [GetNextConnection](#getnextconnection) вызова.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, указывающее начальную позицию для прохода сопоставление; или **NULL** Если сопоставление пусто.  
  
### <a name="remarks"></a>Примечания  
 Порядковый номер итерации не является прогнозируемым; Таким образом «первый элемент в схеме» не имеет особой важности.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CConnectionPoint::GetNextConnection](#getnextconnection).  
  
##  <a name="onadvise"></a>CConnectionPoint::OnAdvise  
 Вызывается платформой, если соединение будет установлено или разорвано.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 `bAdvise`  
 **Значение TRUE,**, если соединение устанавливается; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не выполняет никаких действий.  
  
 Переопределите эту функцию, чтобы получать уведомления при приемники соединиться или отсоединиться от вашей точки подключения.  
  
##  <a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface  
 Извлекает указатель на интерфейс запрошенного приемника.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkSink`  
 Идентификатор запрашиваемого интерфейса приемника.  
  
 `ppInterface`  
 Указатель на указатель на интерфейс, определяемый `pUnkSink`. Если объект не поддерживает этот интерфейс \* `ppInterface` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

