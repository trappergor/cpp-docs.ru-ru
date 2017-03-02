---
title: "Приложения управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 81eb0bcdd8c9d154f62635e7f306cefcf7a15c1b
ms.lasthandoff: 02/24/2017

---
# <a name="application-control"></a>Управление приложением
OLE требует существенного контроля над приложениями и их объекты. OLE системные библиотеки DLL необходимо иметь возможность запуска и автоматически создавать приложения, координировать свои производства и изменение объектов и так далее. Функции в этом разделе соответствия этим требованиям. Помимо, вызываемые OLE системные библиотеки DLL, эти функции иногда должна быть вызвана приложений, а также.  
  
### <a name="application-control"></a>Управление приложением  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Указывает, можно ли завершить приложение.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Получает текущий фильтр сообщений приложения.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Возвращает флаг текущего пользовательского элемента управления.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Устанавливает или снимает флаг пользовательских элементов управления.|  
|[AfxOleLockApp](#afxolelockapp)|Увеличивает счетчик глобального framework числа активных объектов в приложении.|  
|[AfxOleUnlockApp](#afxoleunlockapp)|Уменьшает framework количества активных объектов в приложении.|  
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Регистрирует сервер в системном реестре OLE.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Реализует пользовательский интерфейс для *typename* объекта команды.|  
  
##  <a name="a-nameafxolecanexitappa--afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Указывает, можно ли завершить приложение.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если приложение может завершать работу; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение не завершался при наличии незавершенных ссылок ее объектов. Глобальные функции `AfxOleLockApp` и `AfxOleUnlockApp` увеличения и уменьшения, соответственно, счетчик ссылок на объекты приложения. Приложение не следует прервать, когда этот счетчик не равно нулю. Счетчик отличен от нуля, главное окно приложения скрыт (не уничтожение) при выборе закрытия меню системы или выхода из меню «файл». Платформа вызывает эту функцию **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation&#2;](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h 

##  <a name="a-nameafxolegetmessagefiltera--afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Получает текущий фильтр сообщений приложения.  
  
```   
COleMessageFilter* AFXAPI  AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий фильтр сообщений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для доступа к текущей `COleMessageFilter`-производный объект, так же, как и `AfxGetApp` для доступа к текущего объекта приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation&#3;](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation&#4;](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxwin.h 

##  <a name="a-nameafxolegetuserctrla--afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Возвращает флаг текущего пользовательского элемента управления.  
  
```   
BOOL  AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь может управлять приложения; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Пользователь находится в приложение, если пользователь явно открывается или создается новый документ. Пользователь также является в элементе управления, если не было запущено приложение, системные библиотеки DLL с OLE — другими словами, если пользователь запускает приложение в оболочке системы.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="a-nameafxolesetuserctrla--afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Устанавливает или снимает флаг пользовательских элементов управления, которая рассматривается в справочнике `AfxOleGetUserCtrl`.  
  
```  
void  AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Параметры  
 *bUserCtrl*  
 Указывает, является ли значение или очищаемый флаг пользовательских элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию, когда пользователь создает или загружает документ, но не при загрузке или создана с помощью косвенные действия как загрузка внедренный объект из приложения контейнера документа.  
  
 Эта функция вызывается в том случае, если другие действия в приложении следует поместить пользователя в приложение.  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="a-nameafxolelockappa--afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp  
 Увеличивает счетчик глобального framework числа активных объектов в приложении.  
  
```   
void  AFXAPI  AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает количество объектов в активном в приложении. `AfxOleLockApp` И `AfxOleUnlockApp` функции, соответственно, увеличения и уменьшения этого счетчика.  
  
 Когда пользователь пытается закрыть приложение, имеющее активных объектов — приложение, для которого счетчик активных объектов имеет ненулевое значение — платформа скрывает приложения из представления пользователя вместо полностью завершать работу. `AfxOleCanExitApp` Функция указывает, можно ли завершить приложение.  
  
 Вызов `AfxOleLockApp` из любого объекта, предоставляющего интерфейсы OLE, будет ли нежелательно этот объект будет уничтожен во время по-прежнему используется клиентским приложением. Также вызвать `AfxOleUnlockApp` в деструкторе объекта, который вызывает `AfxOleLockApp` в конструкторе. По умолчанию `COleDocument` (и производные классы) автоматически блокировать и разблокировать приложение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCAutomation&#5;](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="a-nameafxoleunlockappa--afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Уменьшает счетчик framework активных объектов в приложении.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Примечания  
 В разделе `AfxOleLockApp` для получения дополнительных сведений.  
  
 Когда число активных объектов становится равным нулю, **AfxOleOnReleaseAllObjects** вызывается.  
  
### <a name="example"></a>Пример  
 В примере показано [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h  

##  <a name="a-nameafxoleregisterserverclassa--afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
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
 Ссылка на идентификатор сервера OLE класса.  
  
 `lpszClassName`  
 Указатель на строку, содержащую имя класса объектов сервера.  
  
 *lpszShortTypeName*  
 Указатель на строку, содержащую краткое имя типа объекта сервера, таких как «Диаграмма».  
  
 *lpszLongTypeName*  
 Указатель на строку, содержащую длинное имя типа объекта сервера, таких как «Диаграмма Microsoft Excel 5.0.»  
  
 `nAppType`  
 Значение, взятое из **OLE_APPTYPE** перечисления, указывающее тип OLE-приложения. Ниже перечислены возможные значения.  
  
- `OAT_INPLACE_SERVER`Сервер имеет всего сервера пользовательского интерфейса.  
  
- `OAT_SERVER`Сервер поддерживает только внедрения.  
  
- `OAT_CONTAINER`Контейнер поддерживает ссылки на внедряемые объекты.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-поддержкой объекта.  
  
 `rglpszRegister`  
 Массив указателей на строки, представляющие разделы и значения, добавляется к OLE системного реестра, если нет существующего значения для ключей не найдены.  
  
 `rglpszOverwrite`  
 Массив указателей на строки, представляющие ключи и значения для добавления в системный реестр OLE, если существующие значения для ключей, заданного в реестре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если класс server успешно зарегистрировано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Большинство приложений можно использовать **COleTemplateServer::Register** для регистрации типов документа приложения. Если формат системного реестра приложения не помещается стандартным образом, можно использовать `AfxOleRegisterServerClass` для усиления контроля.  
  
 Реестр состоит из набора ключей и значений. `rglpszRegister` И `rglpszOverwrite` аргументы представляют собой массивы указателей на строки, состоящий из ключ и значение разделенные **NULL** символов ( `'\0'`). Каждый из этих строк может содержать подстановочные параметры которого местах помечены последовательности символов `%1` через `%5`.  
  
 Символы будут заполнены следующим образом:  
  
|Символ|Значение|  
|------------|-----------|  
|%1|Идентификатор класса, форматируются как строка|  
|%2|Имя класса|  
|%3|Путь к исполняемому файлу|  
|%4|Краткое имя типа|  
|%5|Имя типа Long|  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxdisp.h

##  <a name="a-nameafxoleseteditmenua--afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 Реализует пользовательский интерфейс для *typename* объекта команды.  
  
```   
void  AFXAPI  AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Параметры  
 `pClient`  
 Указатель на элемент OLE клиента.  
  
 `pMenu`  
 Указатель на объект меню обновляться.  
  
 *iMenuItem*  
 Индекс обновляемого элемента меню.  
  
 `nIDVerbMin`  
 Идентификатор команды, соответствующий первичный глагол.  
  
 *nIDVerbMax*  
 Идентификатор команды, соответствующее последней команды.  
  
 *nIDConvert*  
 Идентификатор для данного элемента меню Convert.  
  
### <a name="remarks"></a>Примечания  
 Если сервер распознает только первичный глагол, пункт меню становится «глагол *typename* объект» и `nIDVerbMin` команда отправляется, когда пользователь выбирает команду. Если сервер распознает несколько команд, а затем пункт меню становится « *typename* объект» и список всех команд подменю отображается при выборе команды. Когда пользователь выбирает команду в подменю `nIDVerbMin` отправляется, если выбирается первая команда, `nIDVerbMin` + 1 отправляется в том случае, если вторая команда будет выбран и т. д. Значение по умолчанию `COleDocument` реализация автоматически обрабатывает эту функцию.  
  
 Необходимо иметь следующую инструкцию в скрипте ресурсов приложения клиента (. Версия-Кандидат) файла.  
  
 **#include \<afxolecl.rc настроек**  

### <a name="requirements"></a>Требования  
 **Заголовок**: afxole.h 

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

