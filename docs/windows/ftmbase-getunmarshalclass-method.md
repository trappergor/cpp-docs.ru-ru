---
title: Метод FtmBase::GetUnmarshalClass | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 329d43227aa131728db72086f99cb86797a5e1e3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571156"
---
# <a name="ftmbasegetunmarshalclass-method"></a>Метод FtmBase::GetUnmarshalClass
Возвращает идентификатор CLSID, модель COM использует для поиска библиотеки DLL, содержащей код для соответствующего прокси-сервера. COM загружает эту библиотеку DLL для создания неинициализированным экземпляром прокси-сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Ссылка на идентификатор интерфейса для маршалинга.  
  
 *PV*  
 Указатель на интерфейс, который должен быть маршалирован; может иметь значение NULL, если вызывающий объект не имеет указатель на нужный интерфейс.  
  
 *dwDestContext*  
 Контекст назначения, где должен быть неупакованный указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 Распаковка может произойти либо в другое подразделение текущего процесса (MSHCTX_INPROC) или в другом процессе на том же компьютере, что и текущий процесс (MSHCTX_LOCAL).  
  
 *pvDestContext*  
 Зарезервировано для будущего использования; должен иметь значение NULL.  
  
 *mshlflags*  
 После завершения этой операции, указатель на идентификатор CLSID, используемый для создания прокси-сервера в клиентском процессе.  
  
 *pCid*  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае значение S_FALSE.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)