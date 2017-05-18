---
title: "Элемент управления приложением | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 5e48437920f56cdfd119c1d703db585616881833
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="application-control"></a>Управление приложением
OLE требуются значительные возможности управления приложений и их объекты. Система OLE библиотеки DLL должна быть возможность запуска и освобождает приложений автоматически, координации их производства и изменением объектов и т. д. Функции, в этом разделе удовлетворять этим требованиям. В дополнение к их вызова OLE системные библиотеки DLL, эти функции должен вызываться иногда также приложениями. 
  
### <a name="application-control"></a>Управление приложением  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Указывает, является ли приложение может завершиться.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Извлекает текущий фильтр сообщений приложения.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Извлекает текущий флаг пользовательского элемента управления.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Устанавливает или снимает флаг пользовательского элемента управления.|  
|[AfxOleLockApp](#afxolelockapp)|Увеличивает число глобальных framework числа активных объектов в приложении.|  
|[AfxOleLockControl](#afxolelockcontrol)| Блокирует фабрики класса указанного элемента управления. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Уменьшает framework количество активных объектов в приложении.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Разблокирует фабрики класса указанного элемента управления. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Регистрирует сервер в системном реестре OLE.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Реализует пользовательский интерфейс для *typename* объекта команды.|  

  
##  <a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Указывает, является ли приложение может завершиться.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если приложение может завершить работу; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение не должно быть прекращено при наличии невыполненные ссылки на его объектов. Глобальные функции `AfxOleLockApp` и `AfxOleUnlockApp` увеличения и уменьшения, соответственно, счетчик ссылок на объекты приложения. Приложение не завершался при этот счетчик не равно нулю. Счетчик имеет ненулевое значение, главное окно приложения скрыто (не уничтожения) когда пользователь выбирает закрыть меню системы или выход из меню «файл». Платформа вызывает эту функцию **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation #2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Извлекает текущий фильтр сообщений приложения.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий фильтр сообщений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для доступ к текущему `COleMessageFilter`-производного объекта, так же, как и `AfxGetApp` для доступа к текущий объект приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation #3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation #4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Извлекает текущий флаг пользовательского элемента управления.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь находится в элементе управления приложения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Пользователь находится в элемент управления приложения, если пользователь явно открыть или создать новый документ. Пользователь также является в элементе управления, если система OLE DLL-библиотеки не было запущено приложение — другими словами, если пользователь запустит приложение в оболочке системы.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Устанавливает или снимает флаг пользовательских элементов управления, который описывается в справочнике `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Параметры  
 *bUserCtrl*  
 Указывает, является ли флаг пользовательских элементов управления для установки или очищено.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию, когда пользователь создает или загружает документ, но не при загрузке или созданы с помощью косвенных действия как загрузка внедренного объекта из приложения контейнера документа.  
  
 Эта функция вызывается в том случае, если другие действия в приложении следует поместить пользователя в элементе управления приложения.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="afxolelockapp"></a>AfxOleLockApp  
 Увеличивает число глобальных framework числа активных объектов в приложении.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает число объектов в активном в приложении. `AfxOleLockApp` И `AfxOleUnlockApp` функции, соответственно, увеличения и уменьшения этого счетчика.  
  
 Когда пользователь пытается закрыть приложение, имеющее активных объектов — приложение, для которого счетчик активных объектов имеет ненулевое значение — платформа скрывает приложения из представления пользователя, а не полностью завершение его работы. `AfxOleCanExitApp` Функции указывает, является ли приложение может завершиться.  
  
 Вызовите `AfxOleLockApp` из любой объект, который предоставляет интерфейсы OLE, если бы он был нежелательных для этого объекта будут удаляться при по-прежнему используется клиентским приложением. Кроме того, вызвать `AfxOleUnlockApp` в деструкторе любой объект, который вызывает `AfxOleLockApp` в конструкторе. По умолчанию `COleDocument` (и производные классы) автоматически блокировать и разблокировать приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation #5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Уменьшает счетчик framework активных объектов в приложении.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Примечания  
 В разделе `AfxOleLockApp` для получения дополнительных сведений.  
  
 Когда число активных объектов достигнет нуля, **AfxOleOnReleaseAllObjects** вызывается.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Блокирует фабрики класса указанного элемента управления динамически созданные данные, связанные с элементом управления остается в памяти.  
   
### <a name="syntax"></a>Синтаксис    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Параметры  
 `clsid`  
 Класс уникальный идентификатор элемента управления.  
  
 `lpszProgID`  
 Уникальный идентификатор программы элемента управления.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика класса элемента управления была успешно заблокирована; в противном случае — 0.  
   
### <a name="remarks"></a>Примечания  
 Это может значительно ускорить отображение элементов управления. Например, после создания элемента управления в диалоговом окне и заблокировать элемент управления с `AfxOleLockControl`, необходимо создать и удалите его заново каждый раз, видима или уничтожения диалогового окна. Если пользователь открывает и закрывает диалоговое окно повторно, блокировки элементов управления может существенно улучшить производительность. Когда будете готовы удалить элемент управления, вызовите `AfxOleUnlockControl`.  
   
### <a name="example"></a>Пример  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Требования  
 **Заголовок:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 Эта функция позволяет зарегистрировать сервер в системном реестре OLE.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Ссылка на идентификатор класса сервера OLE  
  
 `lpszClassName`  
 Указатель на строку, содержащую имя класса объектов сервера.  
  
 *lpszShortTypeName*  
 Указатель на строку, содержащую краткое имя типа объекта сервера, например «Диаграмма».  
  
 *lpszLongTypeName*  
 Указатель на строку, содержащую длинное имя типа объекта сервера, например «Диаграмма Microsoft Excel 5.0.»  
  
 `nAppType`  
 Значение, берется из **OLE_APPTYPE** перечисления, указывающее тип OLE-приложения. Ниже перечислены возможные значения.  
  
- `OAT_INPLACE_SERVER`Сервер имеет всего сервера пользовательского интерфейса.  
  
- `OAT_SERVER`Сервер поддерживает только внедрение.  
  
- `OAT_CONTAINER`Контейнер поддерживает ссылки на внедряемые объекты.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-поддержкой объекта.  
  
 `rglpszRegister`  
 Массив указателей на строки, представляющие ключей и для добавления в системный реестр OLE, если нет существующего значения для ключей не найдены.  
  
 `rglpszOverwrite`  
 Массив указателей на строки, представляющие ключи и значения для добавления в системный реестр OLE, если существующие значения для ключей, заданного в реестре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс server успешно зарегистрировано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Большинство приложений можно использовать **COleTemplateServer::Register** для регистрации типов документов приложения. Если формат системного реестра приложения не соответствует стандартным шаблоном, можно использовать `AfxOleRegisterServerClass` для усиления контроля.  
  
 Реестр состоит из набора ключей и значений. `rglpszRegister` И `rglpszOverwrite` аргументы представляют собой массивы указателей на строки, состоящая из ключа и значения разделенные **NULL** символ ( `'\0'`). Каждая из этих строк может иметь подстановочные параметры которого местах помечаются последовательности символов `%1` через `%5`.  
  
 Символы заполняются следующим образом:  
  
|Символ|Значение|  
|------------|-----------|  
|%1|Идентификатор класса, в формате строки|  
|%2|Имя класса|  
|%3|Путь к исполняемому файлу|  
|%4|Краткое имя типа|  
|%5|Имя типа Long|  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 Реализует пользовательский интерфейс для *typename* объекта команды.  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Параметры  
 `pClient`  
 Указатель на элемент клиента OLE.  
  
 `pMenu`  
 Указатель на объект меню обновляться.  
  
 *iMenuItem*  
 Индекс обновляемого элемента меню.  
  
 `nIDVerbMin`  
 Идентификатор команды, соответствующий первичный глагол.  
  
 *nIDVerbMax*  
 Идентификатор команды, соответствующий последней команды.  
  
 *nIDConvert*  
 Идентификатор для элемента меню Convert.  
  
### <a name="remarks"></a>Примечания  
 Если сервер распознает только первичный глагол, пункт меню становится «глагол *typename* объекта» и `nIDVerbMin` команда отправляется, когда пользователь выбирает команду. Если сервер распознает несколько команд, а затем пункт меню становится « *typename* объекта» и список всех команд подменю появляется, когда пользователь выбирает команду. Когда пользователь выбирает команду в подменю `nIDVerbMin` отправляется, если выбирается первая команда, `nIDVerbMin` + 1 отправляется в том случае, если вторая команда выбранного и т. д. Значение по умолчанию `COleDocument` реализация автоматически обрабатывает эту функцию.  
  
 Необходимо иметь следующую инструкцию в сценарий ресурсов приложения клиента (. Версия-Кандидат) файла.  
  
 **#include \<afxolecl.rc настроек**  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxole.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a>AfxOleUnlockControl
Разблокирует фабрики класса указанного элемента управления.  
   
### <a name="syntax"></a>Синтаксис  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Параметры  
 `clsid`  
 Класс уникальный идентификатор элемента управления.  
  
 `lpszProgID`  
 Уникальный идентификатор программы элемента управления.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика класса элемента управления был успешно разблокирован; в противном случае — 0.  
   
### <a name="remarks"></a>Примечания  
 Элемент управления заблокирован с `AfxOleLockControl`, после чего динамически созданные данные, связанные с элементом управления остается в памяти. Это может значительно ускорить отображение элемента управления, так как не управления должны создаваться и уничтожаться, каждый раз, он отображается. Когда будете готовы удалить элемент управления, вызовите `AfxOleUnlockControl`.  
   
### <a name="example"></a>Пример  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Требования  
 **Заголовок:**<afxwin.h></afxwin.h>  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)


