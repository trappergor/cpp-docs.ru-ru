---
title: "Класс CConnectionPoint | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint class
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a511f252bf921433d070059518e6e67b952680eb
ms.lasthandoff: 02/24/2017

---
# <a name="cconnectionpoint-class"></a>Класс CConnectionPoint
Определяет особый тип интерфейса, используемый для взаимодействия с другими объектами OLE и называемый "точкой подключения".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Создает объект `CConnectionPoint`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](#getconnections)|Извлекает все точки подключения на карте подключения.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Получает контейнер элемента управления, которому принадлежит соединение карты.|  
|[CConnectionPoint::GetIID](#getiid)|Извлекает идентификатор интерфейса точки подключения.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Получает максимальное количество точек соединения, поддерживаемых элементом управления.|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Извлекает указатель на элемент подключения в `pos`.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextConnection` вызова.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Вызывается инфраструктурой при установке или разрыва подключения.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Извлекает указатель на интерфейс запрошенного приемника.|  
  
## <a name="remarks"></a>Примечания  
 В отличие от обычных интерфейсов OLE, которые используются для реализации и предоставляют функциональные возможности элемента управления OLE, точки подключения реализует исходящего интерфейса, который может инициировать действия на другие объекты, такие как запуск событий и уведомлений об изменениях.  
  
 Соединение состоит из двух частей: объект, вызвав интерфейс, называемый «источник» и объект, реализующий интерфейс, называется «приемнику». Путем предоставления точки подключения, источника позволяет приемников для установки подключений к самому себе. Через механизм точек подключения исходный объект получает указатель на реализацию приемника набора функций-членов. Например для порождения события реализации приемником, источник можно вызвать соответствующий метод реализацию приемника.  
  
 По умолчанию `COleControl`-производный класс реализует двумя точками подключения: уведомления об изменениях для события и свойства. Эти соединения служат, соответственно, для события Click и для уведомления приемника (например, элемент управления контейнера) при изменении значения свойства. Также поддерживается для реализации точек подключения дополнительных элементов управления OLE. Для каждой точки дополнительные подключения, реализуется в классе элемента управления необходимо объявить «часть подключения данных», которая реализует точки подключения. Если реализовать один или несколько точек подключения, необходимо также объявить один «сопоставление подключения» в классе элемента управления.  
  
 В следующем примере показано сопоставление простого подключения и одну точку подключения для `Sample` элемента управления OLE, состоящий из двух фрагментов кода: первая часть объявляет сопоставление подключения и точки; второй реализует этот карты и точки. Первый фрагмент вставляется в объявление класса элемента управления, в разделе `protected` раздела:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#7;](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 `BEGIN_CONNECTION_PART` И `END_CONNECTION_PART` макросы объявить класс embedded `XSampleConnPt` (производный от `CConnectionPoint`), реализующий эту точку конкретного подключения. Если требуется переопределить любые `CConnectionPoint` функции-члены, или добавить собственные функции-члены, объявите их между этими двумя макросами. Например `CONNECTION_IID` переопределяет макрос `CConnectionPoint::GetIID` функция-член, помещенный между этими двумя макросами.  
  
 Второй фрагмент кода вставляется в файл реализации (. CPP) класса элемента управления. Этот код реализует карты подключения, которая включает дополнительных подключений, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 После вставки эти фрагменты кода примера OLE элемент управления предоставляет точку подключения для **ISampleSink** интерфейса.  
  
 Как правило точки подключения поддерживает «рассылка», — это возможность выполнять широковещательную рассылку на несколько приемников, которые подключены к тому же интерфейсу. В следующем фрагменте кода показано, как выполнить многоадресную перебирая каждый приемник в точке соединения:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 В этом примере извлекается текущий набор подключений на `SampleConnPt` точку подключения с помощью вызова `CConnectionPoint::GetConnections`. Затем запрос проходит через подключения и вызывает метод `ISampleSink::SinkFunc` для каждого активного подключения.  
  
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
 Указатель на массив активных подключений (приемники). Некоторые указатели в массиве может иметь значение NULL. Каждого указателя отличных от NULL, в этом массиве можно безопасно преобразовать в указатель на интерфейс приемника, с помощью оператора приведения.  
  
##  <a name="getcontainer"></a>CConnectionPoint::GetContainer  
 Вызывается платформой для получения **IConnectionPointContainer** точки подключения.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения указателя в контейнер; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно реализуется `BEGIN_CONNECTION_PART` макрос.  
  
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
 Вызывается платформой для получения максимальное число подключений, поддерживаемого точкой подключения.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное число подключений, поддерживаемых элемент управления или значение -1, если ограничения нет.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает значение -1, указывающее, не ограничено.  
  
 Переопределите эту функцию, если требуется ограничить количество приемников, которые могут подключаться к элементу управления.  
  
##  <a name="getnextconnection"></a>CConnectionPoint::GetNextConnection  
 Извлекает указатель на элемент подключения в `pos`.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Указывает ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNextConnection` или [GetStartPosition](#getstartposition) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент соединения с указанным `pos`, или значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в сопоставление подключения. При выполнении итераций, пропустите все значения NULL, возвращаемых этой функцией.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCConnectionPoints&#4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан [GetNextConnection](#getnextconnection) вызова.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, указывающее начальную позицию для прохода карты; или **NULL** Если сопоставление является пустым.  
  
### <a name="remarks"></a>Примечания  
 Последовательность итерации не является прогнозируемым. Таким образом «первый элемент в сопоставлении» не имеет особой важности.  
  
### <a name="example"></a>Пример  
  В примере показано [CConnectionPoint::GetNextConnection](#getnextconnection).  
  
##  <a name="onadvise"></a>CConnectionPoint::OnAdvise  
 Вызывается инфраструктурой при соединение будет установлено или разорвано.  
  
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
 Указатель на указатель интерфейса, идентифицируемый `pUnkSink`. Если объект не поддерживает этот интерфейс \* `ppInterface` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


