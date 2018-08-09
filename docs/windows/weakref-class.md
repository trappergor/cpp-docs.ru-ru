---
title: Класс WeakRef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88252e6bf4a5b7cad1ee6fcd0580d29f1bf5981a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641837"
---
# <a name="weakref-class"></a>Класс WeakRef
Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>Примечания  
 Объект **WeakRef** поддерживает *строгую ссылку*, которая связана с объектом и может быть допустимой или недопустимой. Вызовите `As()` или `AsIID()` метод, чтобы получить строгую ссылку. Когда строгая ссылка допустима, возможно обращение к связанному объекту. Когда строгая ссылка является недопустимым (**nullptr**), связанный объект недоступен.  
  
 Объект **WeakRef** объекта обычно используется для представления объекта, существование которого управляет внешний поток или приложение. Например, конструкция **WeakRef** объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.  
  
 Обратите внимание на изменение в поведении методов [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) и [CopyTo](../windows/weakref-copyto-method.md) в пакете SDK для Windows 10. Ранее после вызова любого из этих методов, можно проверить для WeakRef **nullptr** для определения того, если строгую ссылку был успешно получен, как показано в следующем коде:  
  
```cpp  
WeakRef wr;  
strongComptrRef.AsWeak(&wr);  
  
// Now suppose that the object strongComPtrRef points to no longer exists  
// and the following code tries to get a strong ref from the weak ref:  
ComPtr<ISomeInterface> strongRef;  
HRESULT hr = wr.As(&strongRef);  
  
// This check won't work with the Windows 10 SDK version of the library.  
// Check the input pointer instead.  
if(wr == nullptr)  
{  
    wprintf(L"Couldn’t get strong ref!");  
}  
```  
  
 Приведенный выше код не работает при использовании пакета SDK для Windows 10 (или более поздней версии). Вместо этого проверьте указатель, который был передан в для **nullptr**.  
  
```cpp  
if (strongRef == nullptr)  
{  
    wprintf(L"Couldn't get strong ref!");  
}  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор WeakRef::WeakRef](../windows/weakref-weakref-constructor.md)|Инициализирует новый экземпляр класса **WeakRef** класса.|  
|[Деструктор WeakRef::~WeakRef](../windows/weakref-tilde-weakref-destructor.md)|Деинициализирует текущий экземпляр **WeakRef** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод WeakRef::As](../windows/weakref-as-method.md)|Задает указанный `ComPtr` параметр-указатель для представления указанного интерфейса.|  
|[Метод WeakRef::AsIID](../windows/weakref-asiid-method.md)|Задает указанный `ComPtr` параметр-указатель для представления идентификатора указанного интерфейса.|  
|[Метод WeakRef::CopyTo](../windows/weakref-copyto-method.md)|Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор WeakRef::operator&](../windows/weakref-operator-ampersand-operator.md)|Возвращает `ComPtrRef` , представляющий текущий **WeakRef** объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)