---
title: Делегат и интерфейс сопоставить макросы (MFC) | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d817ec62734b3646c4df0977daa8161601e5c592
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122696"
---
|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Начинает сопоставление делегатов.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Начинается определение interfaced карты.|
|[Делегат CommandHandler](#commandhandler)|Регистрирует методы обратного вызова источника команды.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Завершает сопоставление делегатов.|
|[END_INTERFACE_MAP](#end_interface_map)|Завершает схему интерфейсов в файле реализации. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Создает запись в схеме делегата.|
|[INTERFACE_PART](#interface_part)|Используется между макросом BEGIN_INTERFACE_MAP и end_interface_map-макрос для каждого интерфейса, поддерживаемого объектом.|
|[MAKE_DELEGATE](#make_delegate)|Присоединяет обработчик событий для управляемого элемента управления.|


## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP
Начинает сопоставление делегатов.  
   
### <a name="syntax"></a>Синтаксис    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>Параметры  
 *КЛАСС*  
 Класс, в котором размещен управляемый элемент управления.  
   
### <a name="remarks"></a>Примечания  
 Этот макрос отмечает начало списка записей делегат, который составляют сопоставление делегатов. Пример использования этого макроса см. в разделе [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** msclr\event.h  
   
### <a name="see-also"></a>См. также  
 [Практическое руководство. Получение событий Windows Forms из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
Начинается определение interfaced карты, при использовании в файл реализации.  
   
### <a name="syntax"></a>Синтаксис    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>Параметры  
 *theClass*  
 Класс, в котором определяется схема интерфейсов.  
  
 *baseClass*  
 Класс, от которого *theClass* является производным от.  
   
### <a name="remarks"></a>Примечания  
 Для каждого интерфейса, реализуемого имеется один или несколько вызовов макросов INTERFACE_PART. Для каждого агрегата, используемого классом имеется один вызов макроса INTERFACE_AGGREGATE.  
  
 Дополнительные сведения о схемы интерфейсов см. в разделе [Технические заметки 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
 
##  <a name="commandhandler"></a>Делегат CommandHandler
Регистрирует методы обратного вызова источника команды.  
   
### <a name="syntax"></a>Синтаксис    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>Параметры  
 *cmdID*  
 Идентификатор команды.  
   
### <a name="remarks"></a>Примечания  
 Этот делегат регистрирует методы обратного вызова источника команды. При добавлении делегат исходный объект команды, метод обратного вызова становится обработчик команд, поступающих из указанного источника.  
  
 Дополнительные сведения см. в разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>См. также  
 [Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>CommandUIHandler
Регистрирует методы обратного вызова с сообщением команды обновления интерфейса пользователя.  
   
### <a name="syntax"></a>Синтаксис    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>Параметры  
 *cmdID*  
 Идентификатор команды.  
  
 *cmdUI*  
 Идентификатор команды сообщения.  
   
### <a name="remarks"></a>Примечания  
 Этот делегат регистрирует методы обратного вызова с сообщением команды обновления интерфейса пользователя. `CommandUIHandler` Аналогично [CommandHandler](#commandhandler) за исключением того, что этот делегат будет использоваться с команд обновление объектов пользовательского интерфейса. Команд обновления интерфейса пользователя должны быть сопоставлены одному с методы обработчика сообщений.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>См. также  
 [Как: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
Завершает сопоставление делегатов.  
   
### <a name="syntax"></a>Синтаксис    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>Примечания  
 Этот макрос отмечает конец список записей делегат, который составляют сопоставление делегатов. Пример использования этого макроса см. в разделе [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** msclr\event.h  
   
### <a name="see-also"></a>См. также  

 [Практическое руководство. Получение событий Windows Forms из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
Завершает схему интерфейсов в файле реализации.  
   
### <a name="syntax"></a>Синтаксис    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о картах интерфейса см. в разделе [Технические заметки 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
Создает запись в схеме делегата.  
   
### <a name="syntax"></a>Синтаксис    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>Параметры  
 *ЧЛЕН*  
 Метод обработчика событий для присоединения к элементу управления.  
  
 *ARG0*  
 Первый аргумент управляемый обработчик событий, таких как `Object^`.  
  
 *ARG1*  
 Второй аргумент управляемый обработчик событий, таких как `EventArgs^`.  
   
### <a name="remarks"></a>Примечания  
 Каждая запись в схеме делегата соответствует делегата обработчика управляемого события, созданные [MAKE_DELEGATE](#make_delegate).  
   
### <a name="example"></a>Пример  
 В следующем примере кода показано, как использовать для создания записи в схеме делегата для EVENT_DELEGATE_ENTRY `OnClick` обработчик событий; см; также в примере кода в MAKE_DELEGATE. Дополнительные сведения см. в разделе [как: приемника событий для Windows Forms из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** msclr\event.h  
   
### <a name="see-also"></a>См. также  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
Используется между макросом BEGIN_INTERFACE_MAP и end_interface_map-макрос для каждого интерфейса, поддерживаемого объектом.  
   
### <a name="syntax"></a>Синтаксис    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>Параметры  
 *theClass*  
 Имя класса, содержащего схему интерфейсов.    
 *IID*  
 Идентификатор IID, сопоставляемое с внедренным классом.    
 *localClass*  
 Имя локального класса.  
   
### <a name="remarks"></a>Примечания  
 Он позволяет сопоставить IID с членом класса, обозначенного *theClass* и *localClass*.  
  
 Дополнительные сведения о схемы интерфейсов см. в разделе [Технические заметки 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
Присоединяет обработчик событий для управляемого элемента управления.  
   
### <a name="syntax"></a>Синтаксис    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>Параметры  
 *ДЕЛЕГАТ*  
 Тип обработчика управляемых событий делегировать, таких как [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).  
  
 *ЧЛЕН*  
 Имя метода обработчика событий, присоединенных к элементу управления.  
   
### <a name="remarks"></a>Примечания  
 Этот макрос создает делегат обработчика управляемого события типа *ДЕЛЕГИРОВАТЬ* и имени *ЧЛЕН*. Делегата обработчика событий управляемого позволяет собственного класса для обработки управляемых событий.  
   
### <a name="example"></a>Пример  
 В следующем примере кода показано, как вызвать `MAKE_DELEGATE` для присоединения `OnClick` обработчик событий для элемента управления MFC `MyControl`. Более широкой описание того, как работает этот макрос в приложениях MFC см. в разделе [как: приемника событий для Windows Forms из собственных классов C++](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>Требования  
 **Заголовок:** msclr\event.h  
   
### <a name="see-also"></a>См. также  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 



