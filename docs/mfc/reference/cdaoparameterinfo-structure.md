---
title: Структура CDaoParameterInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 62addd44f8aa8fceafef6a27244994a2ec6b766b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399789"
---
# <a name="cdaoparameterinfo-structure"></a>Структура CDaoParameterInfo

`CDaoParameterInfo` Структура содержит сведения об объекте параметров, определенных для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет объект параметра. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_nType*<br/>
Значение, указывающее тип данных объекта parameter. Список возможных значений, см. в разделе *m_nType* членом [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.

*m_varValue*<br/>
Значение параметра, хранящиеся в [COleVariant](../../mfc/reference/colevariant-class.md) объекта.

## <a name="remarks"></a>Примечания

Ссылки на первичной и вторичной выше указывают, как возвращаются данные по [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функции-члена в классе `CDaoQueryDef`.

MFC не инкапсулировать объекты параметров DAO в классе. MFC базовых объектов DAO querydef `CDaoQueryDef` объекты хранят параметры в своих коллекциях параметров. Для доступа к объектам параметра в [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) , вызовите объекта querydef `GetParameterInfo` функция-член для определенного параметра имя или индекс в коллекции параметров. Можно использовать [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) функция-член в сочетании с `GetParameterInfo` циклический перебор коллекции параметров.

Сведений, получаемых методом [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функция-член хранится в `CDaoParameterInfo` структуры. Вызовите `GetParameterInfo` для объекта querydef, в которых коллекции параметров хранится объект параметра.

> [!NOTE]
>  Если вы хотите получить или задать только значение параметра, используйте [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) и [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) функции-члены класса `CDaoRecordset`.

`CDaoParameterInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoParameterInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)
