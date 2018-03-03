---
title: "Интерфейс ICommandUI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4971ceaea57b91ff708315a2c32c7bac2801798f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="icommandui-interface"></a>Интерфейс ICommandUI
Управляет команд пользовательского интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[icommandui__Check](#check)|Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.|  
|[ICommandUI::ContinueRouting](#continuerouting)|Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.|  
|[ICommandUI::Enabled](#enabled)|Включает или отключает элементами пользовательского интерфейса для этой команды.|  
|[ICommandUI::ID](#id)|Возвращает идентификатор объекта интерфейса пользователя, представленного `ICommandUI` объекта.|  
|[ICommandUI::Index](#index)|Возвращает индекс объекта интерфейса пользователя, представленного `ICommandUI` объекта.|  
|[ICommandUI::Radio](#radio)|Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.|  
|[ICommandUI::Text](#text)|Задает текст элемента интерфейса пользователя для этой команды.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI`Аналогично [CCmdUI-класс](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, совместимые с компоненты .NET.  
  
 `ICommandUI`используется в рамках `ON_UPDATE_COMMAND_UI` обработчик в [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-производного класса. При активации пользователем приложения (включению или щелчки) меню, каждый элемент меню отображается как включена или отключена. Целевой каждой команды меню предоставляет эти сведения, реализовав `ON_UPDATE_COMMAND_UI` обработчика. Для каждого из объектов интерфейса пользователя команду в приложении используйте окно свойств для создания записи сопоставления сообщения и прототип функции для каждого обработчика.  
  
 Дополнительные сведения о том, как `ICommandUI` интерфейс используется маршрутизация команд см. в разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Дополнительные сведения об управлении команд пользовательского интерфейса в MFC см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
## <a name="check"></a>ICommandUI::Check  
Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.
```
property UICheckState Check;
```
## <a name="remarks"></a>Примечания  
Это свойство задает элемент интерфейса пользователя для этой команды для состояния соответствующего флажка. Установите флажок следующие значения:  
- Снимите 0  
- 1 Проверьте  
- Неопределенное значение 2  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
Указывает механизму маршрутизации команд продолжить маршрутизацию текущее сообщение по цепочке обработчиков.
```
void ContinueRouting();
```
## <a name="remarks"></a>Примечания
Это — это функция дополнительный член, который должен использоваться в сочетании с обработчиком ON_COMMAND_EX, которая возвращает значение FALSE. Дополнительные сведения см. в разделе технической TN006 Примечание: схемы сообщений.

## <a name="enabled"></a>ICommandUI::Enabled 
Включает или отключает элементами пользовательского интерфейса для этой команды.
```
property bool Enabled;
```
## <a name="remarks"></a>Примечания
Это свойство включает или отключает элементами пользовательского интерфейса для этой команды. Включено, чтобы значение true, чтобы включить элемент, значение FALSE, чтобы отключить его.

## <a name="id"></a>ICommandUI::ID  
Возвращает идентификатор объекта интерфейса пользователя, представленного объектом ICommandUI.
```
property unsigned int ID;
```
## <a name="remarks"></a>Примечания
Это свойство возвращает идентификатор (дескриптор) элемент меню, кнопки панели инструментов или другого объекта интерфейса пользователя, представленного объектом ICommandUI.

## <a name="index"></a>ICommandUI::Index   
Возвращает индекс объекта интерфейса пользователя, представленного объектом ICommandUI.
```
property unsigned int Index;
```
## <a name="remarks"></a>Примечания
Это свойство возвращает индекс (дескриптор) элемент меню, кнопки панели инструментов или другого объекта интерфейса пользователя, представленного объектом ICommandUI.

## <a name="radio"></a>ICommandUI::Radio 
Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.
```
property bool Radio;
```
## <a name="remarks"></a>Примечания
Это свойство задает элемент интерфейса пользователя для этой команды для состояния соответствующего флажка. Установите переключатель в true, чтобы включить элемент; в противном случае — значение FALSE.

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
 [Класс CCmdUI](../../mfc/reference/ccmdui-class.md)
