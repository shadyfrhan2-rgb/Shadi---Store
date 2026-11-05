<!-- روبوت شادي - ابدأ -->
<div id="shadi-bot-btn" style="position:fixed;bottom:20px;right:20px;background:#000;color:#FFD700;width:60px;height:60px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:28px;cursor:pointer;z-index:9999;box-shadow:0 4px 15px rgba(0,0,0,0.3);">🤖</div>
<div id="shadi-bot-box" style="display:none;position:fixed;bottom:90px;right:20px;width:320px;max-width:90vw;height:420px;background:white;border-radius:15px;box-shadow:0 5px 25px rgba(0,0,0,0.2);z-index:9999;flex-direction:column;overflow:hidden;">
<div style="background:#000;color:#FFD700;padding:15px;font-weight:bold;text-align:center;">🤖 مساعد شادي ستور</div>
<div id="shadi-chat" style="flex:1;padding:12px;overflow-y:auto;font-size:14px;"></div>
<div style="display:flex;padding:10px;border-top:1px solid #eee;">
<input id="shadi-input" placeholder="اكتب سؤالك..." style="flex:1;padding:10px;border:1px solid #ddd;border-radius:20px;outline:none;">
<button onclick="sendShadi()" style="background:#000;color:#FFD700;border:none;padding:10px 15px;border-radius:20px;margin-right:5px;cursor:pointer;">ارسال</button>
</div>
</div>
<script>
let botBtn = document.getElementById('shadi-bot-btn');
let botBox = document.getElementById('shadi-bot-box');
let chat = document.getElementById('shadi-chat');
botBtn.onclick = function(){ botBox.style.display = botBox.style.display==='none' ? 'flex' : 'none'; if(chat.innerHTML==='') addMsg('اهلا فيك في شادي ستور! 🛍️ وش تدور؟ اكتب "المنتجات" او "الاسعار" او "التوصيل"','bot'); };
function addMsg(t, who){ let d=document.createElement('div'); d.style.cssText = who==='bot' ? 'background:#f1f1f1;padding:8px 12px;border-radius:12px;margin:5px 0;max-width:85%;' : 'background:#000;color:#FFD700;padding:8px 12px;border-radius:12px;margin:5px 0 5px auto;max-width:85%;text-align:right;'; d.textContent=t; chat.appendChild(d); chat.scrollTop=chat.scrollHeight; }
function sendShadi(){ let inp=document.getElementById('shadi-input'); let q=inp.value.trim(); if(!q) return; addMsg(q,'user'); inp.value=''; setTimeout(()=>{ let a=q.toLowerCase(); let r='تواصل معنا على واتساب للطلب، بنرد عليك بسرعة!'; if(a.includes('منتجات')||a.includes('عندك')) r='عندنا تشكيلة حلوة! ارسل لنا على واتساب وبنرسل لك كل المنتجات بالصور والاسعار.'; else if(a.includes('سعر')||a.includes('كم')) r='الاسعار تبدأ من اسعار مناسبة جدا! اي منتج حابه؟ اكتب اسمه.'; else if(a.includes('توصيل')||a.includes('شحن')) r='نوصل لكل المحافظات! التوصيل سريع خلال 1-3 ايام.'; else if(a.includes('سلام')||a.includes('هلا')||a.includes('مرحبا')) r='هلا والله نورت متجر شادي! 😍 وش حاب تشتري اليوم؟'; addMsg(r,'bot'); },500); }
</script>
<!-- روبوت شادي - انتهى -->
