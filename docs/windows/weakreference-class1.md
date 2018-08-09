---
title: WeakReference Class1 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71de341be0cb482a49cbf35ddd34e414be8afde4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645546"
---
# <a name="weakreference-class1"></a>WeakReference Class1
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет *слабую ссылку* , можно использовать с помощью среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.  
  
 Объект **WeakReference** поддерживает *строгую ссылку*, которой является указателем на объект и *число строгую ссылку*, то есть числа копий со строгими ссылки, которые были распространены, `Resolve()` метод. Несмотря на то ненулевое число строгую ссылку, строгая ссылка является действительной и объект доступен. Надежный счетчик достигает нуля, строгая ссылка является недопустимым, и объект недоступен.  
  
 Объект **WeakReference** объекта обычно используется для представления объекта, существование которого управляет внешний поток или приложение. Например, конструкция **WeakReference** объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.  
  
 **WeakReference** методы являются потокобезопасными.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор WeakReference::WeakReference](../windows/weakreference-weakreference-constructor.md)|Инициализирует новый экземпляр класса **WeakReference** класса.|  
|[Деструктор WeakReference::~WeakReference](../windows/weakreference-tilde-weakreference-destructor.md)|Деинициализирует (уничтожает) текущий экземпляр **WeakReference** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод WeakReference::DecrementStrongReference](../windows/weakreference-decrementstrongreference-method.md)|Уменьшает текущий счетчик строгая ссылка **WeakReference** объекта.|  
|[Метод WeakReference::IncrementStrongReference](../windows/weakreference-incrementstrongreference-method.md)|Увеличивает счетчик строгую ссылку текущего **WeakReference** объекта.|  
|[Метод WeakReference::Resolve](../windows/weakreference-resolve-method.md)|Устанавливает заданный указатель в текущее значение строгую ссылку, если строгую ссылку count не равно нулю.|  
|[Метод WeakReference::SetUnknown](../windows/weakreference-setunknown-method.md)|Задает строгая ссылка текущего **WeakReference** объект в заданный указатель интерфейса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WeakReference`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)