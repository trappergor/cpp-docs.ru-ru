---
title: Структура CDaoParameterInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 4f0ee7ebe1d5d4eff50194c2d5c5cccf8f373c61
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096083"
---
# <a name="cdaoparameterinfo-structure"></a>Структура CDaoParameterInfo

`CDaoParameterInfo` Структура содержит сведения об объекте параметра, определенном для объектов доступа к данным (DAO).
Версия DAO 3,6 является окончательной и считается устаревшей.


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
Уникально именует объект параметра. Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_nType*<br/>
Значение типа, указывающее тип данных объекта параметра. Список возможных значений см. в описании элемента *m_nType* структуры [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) . Дополнительные сведения см. в разделе "свойство Type" справки DAO.

*m_varValue*<br/>
Значение параметра, хранящееся в объекте [COleVariant](../../mfc/reference/colevariant-class.md) .

## <a name="remarks"></a>Примечания

Ссылки на первичный и вторичный выше указывают, как эта информация возвращается функцией-членом [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) в `CDaoQueryDef`классе.

MFC не инкапсулирует объекты параметров DAO в классе. Объекты DAO QueryDef. базовые `CDaoQueryDef` объекты MFC хранят параметры в коллекциях параметров. Чтобы получить доступ к объектам параметров в объекте [кдаокуеридеф](../../mfc/reference/cdaoquerydef-class.md) , вызовите функцию- `GetParameterInfo` член объекта QueryDef для определенного имени параметра или индекса в коллекции Parameters. Вы можете использовать функцию-член [кдаокуеридеф:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) в сочетании с `GetParameterInfo` , чтобы прокручивать коллекцию Parameters.

Сведения, получаемые функцией-членом [кдаокуеридеф:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) , хранятся `CDaoParameterInfo` в структуре. Вызовите `GetParameterInfo` объект QueryDef, в коллекции параметров которого хранится объект Parameter.

> [!NOTE]
>  Если необходимо получить или задать только значение параметра, используйте функции-члены [жетпарамвалуе](../../mfc/reference/cdaorecordset-class.md#getparamvalue) и [сетпарамвалуе](../../mfc/reference/cdaorecordset-class.md#setparamvalue) класса `CDaoRecordset`.

`CDaoParameterInfo`также определяет функцию `Dump` -член в отладочных сборках. Можно использовать `Dump` для дампа содержимого `CDaoParameterInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)
