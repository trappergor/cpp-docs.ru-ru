---
title: Класс ActivationFactory | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43e4932f93c4b9954343df2aecd4db3b13ebc147
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649209"
---
# <a name="activationfactory-class"></a>ActivationFactory - класс
Позволяет одному или нескольким классам быть активированными средой выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
### <a name="parameters"></a>Параметры  
 *I0*  
 Интерфейс признаками.  
  
 *I1*  
 Первый интерфейс.  
  
 *I2*  
 Второй интерфейс.  
  
## <a name="remarks"></a>Примечания  
 **ActivationFactory** предоставляет методы регистрации и базовые функциональные возможности для `IActivationFactory` интерфейс. **ActivationFactory** также предоставляет возможность реализации пользовательской фабрики.  
  
 В следующем фрагменте кода символически описывается использование ActivationFactory.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 В следующем фрагменте кода показано, как использовать [реализует](../windows/implements-structure.md) структуры, чтобы указать более чем на три ИД интерфейса.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор ActivationFactory::ActivationFactory](../windows/activationfactory-activationfactory-constructor.md)|Инициализирует **ActivationFactory** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод ActivationFactory::AddRef](../windows/activationfactory-addref-method.md)|Увеличивает счетчик ссылок текущего **ActivationFactory** объекта.|  
|[Метод ActivationFactory::GetIids](../windows/activationfactory-getiids-method.md)|Извлекает массив идентификаторов реализованного интерфейса.|  
|[Метод ActivationFactory::GetRuntimeClassName](../windows/activationfactory-getruntimeclassname-method.md)|Получает имя класса среды выполнения объекта, который текущего **ActivationFactory** создает экземпляр.|  
|[Метод ActivationFactory::GetTrustLevel](../windows/activationfactory-gettrustlevel-method.md)|Получает уровень доверия объект, текущий **ActivationFactory** создает экземпляр.|  
|[Метод ActivationFactory::QueryInterface](../windows/activationfactory-queryinterface-method.md)|Извлекает указатель на указанный интерфейс.|  
|[Метод ActivationFactory::Release](../windows/activationfactory-release-method.md)|Уменьшает счетчик ссылок текущего **ActivationFactory** объекта.|  
  
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
  
 `ActivationFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)