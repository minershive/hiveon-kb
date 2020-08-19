---
title: Проблема с райзером
parent_category: Исправление проблем
path: /troubleshooting-riser_ru
lang: ru
parent_category_path: /troubleshooting_ru
order: 1
meta_description: Проблема с райзером? Мы подскажем, что именно может быть не так.
---

Ошибка выглядит вот так:

<pre><code>
[drm:amdgpu_ib_ring_tests] *ERROR* amdgpu: failed testing IB on
ring 1 (-110).
[drm:amdgpu_vce_ring_test_ib] *ERROR* amdgpu: IB test timed out.
[drm:amdgpu_ib_ring_tests] *ERROR* amdgpu: failed testing IB on
ring 2 (-110).
[drm:amdgpu_vce_ring_test_ib] *ERROR* amdgpu: IB test timed out.
[drm:amdgpu_ib_ring_tests] *ERROR* amdgpu: failed testing IB on
ring 3 (-110).
[drm:amdgpu_vce_ring_test_ib] *ERROR* amdgpu: IB test timed out.
[drm:amdgpu_ib_ring_tests] *ERROR* amdgpu: failed testing IB on
ring 4 (-110).
[drm:amdgpu_vce_ring_test_ib] *ERROR* amdgpu: IB test timed out.
</code></pre>

<img src="https://lbd.hiveos.farm/kbase/images/forum/99qk8b6zmgd3.jpg">

Причина заключается в плохой пайке или даже ломаной линии на райзере. Третья справа на картинке:
<img src="https://lbd.hiveos.farm/kbase/images/forum/ri4qyuscvule.jpg">

И ещё один пример:
<img src="https://lbd.hiveos.farm/kbase/images/forum/5iou6v3fha84.jpg">
