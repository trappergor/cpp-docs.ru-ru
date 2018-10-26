---
title: Интерфейс ICommandUI | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd9ea4397c655f0ebb28d10febe82581d6ad8771
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055012"
---
# <a name="icommandui-interface"></a>Интерфейс ICommandUI

Управляет команд пользовательского интерфейса.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandUI
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[icommandui__Check](#check)|Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.|
|[ICommandUI::ContinueRouting](#continuerouting)|Указывает механизму маршрутизации команд продолжать маршрутизацию текущее сообщение по цепочке обработчиков.|
|[ICommandUI::Enabled](#enabled)|Включает или отключает элемент интерфейса пользователя для этой команды.|
|[ICommandUI::ID](#id)|Получает идентификатор объекта пользовательского интерфейса, представленного `ICommandUI` объекта.|
|[ICommandUI::Index](#index)|Получает индекс объекта пользовательского интерфейса, представленного `ICommandUI` объекта.|
|[ICommandUI::Radio](#radio)|Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.|
|[ICommandUI::Text](#text)|Задает текст элемента интерфейса пользователя для этой команды.|

## <a name="remarks"></a>Примечания

Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI` аналогичен [класс CCmdUI](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, взаимодействие с компонентами .NET.

`ICommandUI` используется в обработчике ON_UPDATE_COMMAND_UI в [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-производного класса. При активации пользователем приложения (выбирает или щелчков мыши) меню, а каждый пункт меню отображается как включена или отключена. Целевой объект каждой команды меню предоставляет эти сведения, реализация обработчика ON_UPDATE_COMMAND_UI. Для каждого из объектов пользовательского интерфейса команды в приложении используйте окно свойств для создания записи схемы сообщений и прототип функции для каждого обработчика.

Дополнительные сведения о том, как `ICommandUI` в маршрутизации команд используется интерфейс, см. в разделе [как: Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Дополнительные сведения о об управлении команд пользовательского интерфейса в MFC, см. в разделе [класс CCmdUI](../../mfc/reference/ccmdui-class.md).

## <a name="check"></a> ICommandUI::Check

Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.
```
property UICheckState Check;
```

## <a name="remarks"></a>Примечания

Это свойство задает элемент пользовательского интерфейса для этой команды для проверки соответствующего состояния. Проверка набора следующие значения:
- Снимите флажок 0
- Проверка 1
- 2 задано неопределенное

## <a name="continuerouting"></a> ICommandUI::ContinueRouting

Указывает механизму маршрутизации команды продолжить маршрутизацию текущее сообщение по цепочке обработчиков.
```
void ContinueRouting();
```

## <a name="remarks"></a>Примечания

Это функция дополнительный член, который должен использоваться в сочетании с обработчик ON_COMMAND_EX, который возвращает значение FALSE. Дополнительные сведения см. в разделе технических TN006 Примечание: схемы сообщений.

## <a name="enabled"></a> ICommandUI::Enabled

Включает или отключает элемент интерфейса пользователя для этой команды.
```
property bool Enabled;
```

## <a name="remarks"></a>Примечания

Это свойство включает или отключает элемент интерфейса пользователя для этой команды. Задайте Enabled в true, чтобы включить элемент, значение FALSE, чтобы отключить его.

## <a name="id"></a> ICommandUI::ID

Получает идентификатор объекта пользовательского интерфейса, представленный объектом ICommandUI.
```
property unsigned int ID;
```

## <a name="remarks"></a>Примечания

Это свойство получает идентификатор (дескриптор) пункта меню, кнопки панели инструментов или других объекта пользовательского интерфейса, представленный объектом ICommandUI.

## <a name="index"></a> ICommandUI::Index

Получает индекс объекта пользовательского интерфейса, представленный объектом ICommandUI.
```
property unsigned int Index;
```

## <a name="remarks"></a>Примечания

Это свойство возвращает индекс пункта меню, кнопки панели инструментов или других объекта пользовательского интерфейса, представленный объектом ICommandUI (дескриптор).

## <a name="radio"></a> ICommandUI::Radio

Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.
```
property bool Radio;
```

## <a name="remarks"></a>Примечания

Это свойство задает элемент пользовательского интерфейса для этой команды для проверки соответствующего состояния. Установите переключатель в true, чтобы включить элемент; в противном случае — значение FALSE.

## <a name="text"></a> ICommandUI::Text

Задает текст элемента интерфейса пользователя для этой команды.
```
property String^ Text;
```

## <a name="remarks"></a>Примечания

Это свойство задает текст элемента интерфейса пользователя для этой команды. Задать текст на дескриптор строки текста.

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определенных в сборке atlmfc\lib\mfcmifc80.dll)

## <a name="see-also"></a>См. также

[Класс CCmdUI](../../mfc/reference/ccmdui-class.md)
