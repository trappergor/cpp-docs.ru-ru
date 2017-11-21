---
title: "Класс ClassFactory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory
dev_langs: C++
helpviewer_keywords: ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c1dfeafab3ffa3c9a25c5c2284f6ca2c047a6c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="classfactory-class"></a>ClassFactory - класс
Реализует базовую функциональность интерфейса IClassFactory.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `I0`  
 Интерфейс нулевой.  
  
 `I1`  
 Первый интерфейс.  
  
 `I2`  
 Второй интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Использовать `ClassFactory` для реализации пользовательской фабрики.  
  
 Следующий шаблон программирования демонстрируется использование [реализует](../windows/implements-structure.md) структура для указания более трех интерфейсов на фабрику классов.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор ClassFactory::ClassFactory](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ClassFactory::AddRef](../windows/classfactory-addref-method.md)|Увеличивает счетчик ссылок для текущим объектом ClassFactory.|  
|[Метод ClassFactory::LockServer](../windows/classfactory-lockserver-method.md)|Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим объектом ClassFactory.|  
|[Метод ClassFactory::QueryInterface](../windows/classfactory-queryinterface-method.md)|Извлекает указатель на интерфейс, определяемый параметром.|  
|[Метод ClassFactory::Release](../windows/classfactory-release-method.md)|Уменьшает счетчик ссылок для текущим объектом ClassFactory.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md)