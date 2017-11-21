---
title: "WeakReference Class1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference
dev_langs: C++
helpviewer_keywords: WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb8e05ca3ef52515af58db455ed83da593d6bdfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="weakreference-class1"></a>Класс WeakReference 1
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class WeakReference;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет *слабой ссылки* может использоваться с среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.  
  
 Объект `WeakReference` сохраняет *строгую ссылку*, которой является указателем на объект и *число строгую ссылку*, число копий строгой ссылки, которые были распространены, метод Resolve(). Хотя количество строгая ссылка имеет ненулевое значение, строгая ссылка является действительной и объект доступен. Если надежный счетчик становится равным нулю, строгая ссылка недопустима и объект недоступен.  
  
 Объект WeakReference, обычно используется для представления объекта, наличием которого управляет внешний поток или приложение. Например можно создайте объект WeakReference из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.  
  
 WeakReference методы являются потокобезопасными.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор WeakReference::WeakReference](../windows/weakreference-weakreference-constructor.md)|Инициализирует новый экземпляр класса WeakReference.|  
|[Деструктор WeakReference::~WeakReference](../windows/weakreference-tilde-weakreference-destructor.md)|Деинициализирует (уничтожает) текущий экземпляр класса WeakReference.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод WeakReference::DecrementStrongReference](../windows/weakreference-decrementstrongreference-method.md)|Уменьшает счетчик строгого ссылок объекта WeakReference.|  
|[Метод WeakReference::IncrementStrongReference](../windows/weakreference-incrementstrongreference-method.md)|Увеличивает счетчик строгую ссылку объекта WeakReference.|  
|[Метод WeakReference::Resolve](../windows/weakreference-resolve-method.md)|Устанавливает заданный указатель текущее значение строгую ссылку, если число строгая ссылка имеет ненулевое значение.|  
|[Метод WeakReference::SetUnknown](../windows/weakreference-setunknown-method.md)|Устанавливает заданный указатель интерфейса строгую ссылку объекта WeakReference.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `WeakReference`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)