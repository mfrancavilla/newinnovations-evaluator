# New Innovations Auto-Fill Bookmarklet

A bookmarklet to automatically fill evaluation forms on New Innovations based on detected PL level or user-selected score.

---

## Install
### One‑click install

Drag the button below to your bookmarks bar:

<a href="javascript:(function(){const t=&quot;https://www.new-innov.com/EvaluationForms/EvaluationFormsHost.aspx&quot;;if(!location.href.startsWith(t)){alert(&quot;Redirecting to evaluation page. After login/load, click bookmark again.&quot;);location.href=t;return;}console.clear();const O={0:&quot;Never&quot;,1:&quot;Rarely&quot;,2:&quot;Sometimes&quot;,3:&quot;Often&quot;,4:&quot;Consistently&quot;,5:&quot;Always&quot;};let p=Array.from(document.querySelectorAll(&quot;.mi-detail-item&quot;)).find(e=&gt;/PL-\d/.test(e.textContent)),d=p?parseInt(p.textContent.match(/PL-(\d)/)[1]):null;if(d===null){console.error(&quot;PL not found&quot;);return;}let i=prompt(`Detected PL-${d}\nEnter score (0–5):`,d),c=i!==null&amp;&amp;i!==&quot;&quot;?Math.max(0,Math.min(5,parseInt(i))):d,b=document.querySelectorAll(&quot;.rating-scale-content&quot;),f=0;b.forEach(x=&gt;{let s=x.querySelectorAll(&quot;.slick-slide&quot;),t=s[c];if(!t)return;let r=t.querySelector(&quot;input[type='radio']&quot;);r&amp;&amp;(r.checked=true,r.dispatchEvent(new Event(&quot;change&quot;,{bubbles:true})),r.dispatchEvent(new Event(&quot;click&quot;,{bubbles:true})),f++)});let e=document.querySelector(&quot;.mi-evaluator&quot;);if(!e){console.warn(&quot;mi-evaluator not found&quot;);return;}let ex=document.getElementById(&quot;auto-fill-status&quot;);ex&amp;&amp;ex.remove();let st=document.createElement(&quot;div&quot;);st.id=&quot;auto-fill-status&quot;;st.textContent=`Auto-filled ${f} with &quot;${O[c]}&quot; (PL-${d})`;st.style.color=&quot;red&quot;;st.style.fontWeight=&quot;bold&quot;;st.style.marginTop=&quot;8px&quot;;e.appendChild(st);})();" 
style="display:inline-block;padding:10px 16px;background:#2563eb;color:#fff;border-radius:8px;text-decoration:none;font-weight:bold;">
Install Auto‑Fill Bookmarklet
</a>

### Manual installation:
1. Create a new bookmark in your browser. Add it to the bookmark bar for convenience.
2. Name it something like:  
   `Auto Fill Evaluations`  
3. Copy **everything below** and paste it into the bookmark **URL/location field**

```
javascript:(function(){const t="https://www.new-innov.com/EvaluationForms/EvaluationFormsHost.aspx";if(!location.href.startsWith(t)){alert("Redirecting to evaluation page. After login/load, click bookmark again.");location.href=t;return;}console.clear();const O={0:"Never",1:"Rarely",2:"Sometimes",3:"Often",4:"Consistently",5:"Always"};let p=Array.from(document.querySelectorAll(".mi-detail-item")).find(e=>/PL-\d/.test(e.textContent)),d=p?parseInt(p.textContent.match(/PL-(\d)/)[1]):null;if(d===null){console.error("PL not found");return;}let i=prompt(`Detected PL-${d}\nEnter score (0–5):`,d),c=i!==null&&i!==""?Math.max(0,Math.min(5,parseInt(i))):d,b=document.querySelectorAll(".rating-scale-content"),f=0;b.forEach(x=>{let s=x.querySelectorAll(".slick-slide"),t=s[c];if(!t)return;let r=t.querySelector("input[type='radio']");r&&(r.checked=true,r.dispatchEvent(new Event("change",{bubbles:true})),r.dispatchEvent(new Event("click",{bubbles:true})),f++)});let e=document.querySelector(".mi-evaluator");if(!e){console.warn("mi-evaluator not found");return;}let ex=document.getElementById("auto-fill-status");ex&&ex.remove();let st=document.createElement("div");st.id="auto-fill-status";st.textContent=`Auto-filled ${f} with "${O[c]}" (PL-${d})`;st.style.color="red";st.style.fontWeight="bold";st.style.marginTop="8px";e.appendChild(st);})();
```
---

## Usage

1. Go to:  
   https://www.new-innov.com/EvaluationForms/EvaluationFormsHost.aspx  

2. Click the bookmarklet  

3. If not already on the page:
   - You will be redirected
   - Click the bookmark **again after the page loads**

4. When prompted:
   - Accept detected level, or
   - Enter a score from **0–5**

5. Change specific evaluations as you see fit.
 
7. Enter comments (the most important part).

9. Click Submit.

---

## What it does

- Detects `PL-#` level automatically  
- Lets you override with manual input  
- Fills all rating fields consistently  
- Displays confirmation on the page

---

## Firefox Notes

- Works in Firefox and Chrome  
- Ensure:
  - The bookmark starts with `javascript:`
  - The code is pasted as a **single line** (this version already is)
- If nothing happens:
  - Re-save the bookmark manually (Firefox sometimes strips formatting)

---

## Disclaimer

This tool is provided for convenience. Use responsibly and ensure evaluations remain accurate and professional.
