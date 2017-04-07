---
title: "Интерфейс ICommandUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>Интерфейс ICommandUI
Управляет команд пользовательского интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[icommandui__Check](#check)|Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.|  
|[ICommandUI::Enabled](#enabled)|Включает или отключает элемент интерфейса пользователя для этой команды.|  
|[ICommandUI::ID](#id)|Получает идентификатор объекта интерфейса пользователя, представленного `ICommandUI` объекта.|  
|[ICommandUI::Index](#index)|Возвращает индекс объекта интерфейса пользователя, представленного `ICommandUI` объекта.|  
|[ICommandUI::Radio](#radio)|Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.|  
|[ICommandUI::Text](#text)|Задает текст элемента интерфейса пользователя для этой команды.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI`Аналогично [класс CCmdUI](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, взаимодействие с компонентами .NET.  
  
 `ICommandUI`используется в `ON_UPDATE_COMMAND_UI` обработчик в [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-производного класса. При активировании пользователем приложения (выбирает или щелчков мышью) меню, каждый элемент меню отображается как включен или отключен. Цель каждой команде меню предоставляет эти сведения при реализации `ON_UPDATE_COMMAND_UI` обработчика. Для каждого объекты команд пользовательского интерфейса в приложении используйте окно свойств для создания записи сопоставления сообщений и прототип функции для каждого обработчика.  
  
 Дополнительные сведения о том, как `ICommandUI` интерфейс используется маршрутизация команд см. в разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Дополнительные сведения об управлении команд пользовательского интерфейса в MFC см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.
```
property UICheckState Check;
```
## <a name="remarks"></a>Примечания  
Это свойство задает элемент интерфейса пользователя для этой команды для соответствующих проверки состояния. Настроить проверку следующие значения:  
- Снимите флажок&0;  
- Проверка&1;  
- Неопределенное значение&2;  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.
```
void ContinueRouting();
```
## <a name="remarks"></a>Примечания
Это функция-член дополнительно, следует использовать в сочетании с обработчиком ON_COMMAND_EX, который возвращает значение FALSE. Дополнительные сведения см. в разделе технических TN006 Примечание: схемы сообщений.

## <a name="enabled"></a>ICommandUI::Enabled 
Включает или отключает элемент интерфейса пользователя для этой команды.
```
property bool Enabled;
```
## <a name="remarks"></a>Примечания
Это свойство включает или отключает элемент интерфейса пользователя для этой команды. Включено в значение true, чтобы включить элемент, значение FALSE, чтобы отключить его.

## <a name="id"></a>ICommandUI::ID  
Возвращает идентификатор объекта интерфейса пользователя, представленного объектом ICommandUI.
```
property unsigned int ID;
```
## <a name="remarks"></a>Примечания
Это свойство возвращает идентификатор элемента меню, кнопки панели инструментов или другой объект интерфейса пользователя, представленный объектом ICommandUI (дескриптор).

## <a name="index"></a>ICommandUI::Index   
Возвращает индекс объекта интерфейса пользователя, представленного объектом ICommandUI.
```
property unsigned int Index;
```
## <a name="remarks"></a>Примечания
Это свойство возвращает индекс (дескриптор) элемент меню, кнопки панели инструментов или другой объект интерфейса пользователя, представленный объектом ICommandUI.

## <a name="radio"></a>ICommandUI::Radio 
Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.
```
property bool Radio;
```
## <a name="remarks"></a>Примечания
Это свойство задает элемент интерфейса пользователя для этой команды для соответствующих проверки состояния. Установите переключатель в true, чтобы включить элемент; в противном случае — значение FALSE.

## <a name="text"></a>ICommandUI::Text 
Задает текст элемента интерфейса пользователя для этой команды.
```
property String^ Text;
```
## <a name="remarks"></a>Примечания
Это свойство задает текст элемента интерфейса пользователя для этой команды. Задать текст дескриптор строки текста.

## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
  
## <a name="see-also"></a>См. также  
 [CCmdUI-класс](../../mfc/reference/ccmdui-class.md)

