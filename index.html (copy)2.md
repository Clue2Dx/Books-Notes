```html
<!doctype html>
<html lang="en"><head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Library">
<meta name="theme-color" content="#f6f5f2">
<link rel="manifest" href="manifest.webmanifest">
<title>Book Library</title>
<style>
:root{--bg:#f6f5f2;--card:#fff;--ink:#1d2327;--mute:#6b747a;--line:#e3e1db;--acc:#2f6f6a;--accbg:#e4efed;--danger:#b3412f;color-scheme:light dark}
@media(prefers-color-scheme:dark){:root{--bg:#141718;--card:#1c2022;--ink:#e8eaea;--mute:#8d979c;--line:#2a3033;--acc:#6fb3ab;--accbg:#223331;--danger:#e07a68}}
*{box-sizing:border-box}[hidden]{display:none!important}
body{margin:0;background:var(--bg);color:var(--ink);font:16px/1.5 -apple-system,system-ui,"Segoe UI",sans-serif;padding:env(safe-area-inset-top) env(safe-area-inset-right) 0 env(safe-area-inset-left)}
header{position:sticky;top:0;background:var(--bg);padding:10px 14px 8px;border-bottom:1px solid var(--line);z-index:5}
.top{display:flex;align-items:center;gap:10px}.top h1{font:600 20px Georgia,"Iowan Old Style",serif;margin:0}
button{font:inherit;color:inherit;background:none;border:0;cursor:pointer;padding:8px 10px;border-radius:8px}
#menu{font-size:22px;padding:4px 8px}
input,select,textarea{font:inherit;color:inherit;background:var(--card);border:1px solid var(--line);border-radius:8px;padding:9px 10px;width:100%}
#q{margin-top:8px}
main{padding:6px 14px 110px;max-width:760px;margin:auto}
h3{font:600 15px Georgia,serif;color:var(--acc);margin:22px 0 4px}
ul{list-style:none;margin:0;padding:0}
.row{display:flex;justify-content:space-between;gap:12px;padding:11px 0;border-bottom:1px solid var(--line);cursor:pointer}
.t{font-family:Georgia,serif;font-size:17px}.s,.m2{color:var(--mute);font-size:13px}.m{display:flex;flex-direction:column;align-items:flex-end;font-size:13px;color:var(--mute);white-space:nowrap}
.pill{padding:1px 8px;border-radius:99px;background:var(--line)}.pill.read{background:var(--accbg);color:var(--acc)}.pill.in_progress{border:1px solid var(--acc);background:none;color:var(--acc)}
.tabs{display:flex;gap:6px;margin:12px 0}.tabs button{border:1px solid var(--line)}.tabs .on{background:var(--accbg);color:var(--acc);border-color:var(--acc)}
.yr{display:flex;align-items:center;justify-content:center;gap:16px;margin:8px 0}.yr button{font-size:22px}
.empty{color:var(--mute);padding:24px 0;text-align:center}
details{border-bottom:1px solid var(--line)}summary{font:600 19px Georgia,serif;padding:12px 0;cursor:pointer}
.flt{margin:12px 0}
#fab{position:fixed;right:18px;bottom:calc(18px + env(safe-area-inset-bottom));width:56px;height:56px;border-radius:50%;background:var(--acc);color:var(--bg);font-size:30px;padding:0;box-shadow:0 2px 10px #0004}
.bg{position:fixed;inset:0;background:#0006;z-index:20}
#side nav{position:fixed;z-index:21;top:0;bottom:0;left:0;width:78%;max-width:300px;background:var(--card);padding:calc(20px + env(safe-area-inset-top)) 14px 20px;display:flex;flex-direction:column;gap:4px}
#side nav h1{font:600 22px Georgia,serif;margin:0 0 14px}#side nav button{text-align:start;font-size:17px}.sp{flex:1}
#sheet .card{position:fixed;z-index:31;left:0;right:0;bottom:0;max-height:92vh;overflow:auto;background:var(--bg);border-radius:16px 16px 0 0;padding:16px 16px calc(16px + env(safe-area-inset-bottom));max-width:760px;margin:auto}
#sheet .bg{z-index:30}
label{display:block;font-size:13px;color:var(--mute);margin:10px 0}label>*{margin-top:4px;color:var(--ink)}
.bar{display:flex;gap:8px;justify-content:flex-end;margin-top:16px}.pri{background:var(--acc);color:var(--bg)}.ghost{border:1px solid var(--line)}.danger{color:var(--danger);margin-inline-end:auto}
.rr{display:flex;gap:6px;margin:6px 0}.x{color:var(--mute)}
#npage{position:fixed;inset:0;z-index:25;background:var(--bg);display:flex;flex-direction:column;padding:env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left)}
#npage .nb{display:flex;justify-content:space-between;padding:8px 10px;border-bottom:1px solid var(--line)}#npage .nb button{font-size:20px}
#npage .nw{flex:1;display:flex;flex-direction:column;max-width:760px;width:100%;margin:auto;padding:14px 18px;min-height:0}
#nt{border:0;background:none;font:600 24px Georgia,serif;padding:0;outline:0}#nm{color:var(--mute);font-size:12px;margin:2px 0 12px;min-height:1em}
#nc{flex:1;border:0;background:none;resize:none;padding:0;font-size:17px;line-height:1.7;outline:0}
.sn{font-size:15px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.row>div:first-child{min-width:0}
#toast{position:fixed;z-index:40;left:50%;transform:translateX(-50%);bottom:90px;background:var(--ink);color:var(--bg);padding:8px 14px;border-radius:99px}
#login{max-width:340px;margin:18vh auto;padding:0 20px}#login h1{font:600 26px Georgia,serif}#login input{margin:6px 0}#err{color:var(--danger);font-size:14px}
</style></head><body>
<div id="login" hidden><h1>Book Library</h1><form id="lf"><input id="em" type="email" placeholder="Email" autocomplete="username" required><input id="pw" type="password" placeholder="Password" autocomplete="current-password" required><p id="err"></p><button class="pri" style="width:100%">Sign in</button></form></div>
<div id="app" hidden>
<header><div class="top"><button id="menu" data-act="menu" aria-label="Menu">☰</button><h1 id="title"></h1></div><input id="q" type="search" dir="auto" placeholder="Search books, authors, notes"></header>
<main id="main"></main>
<button id="fab" data-act="add" aria-label="Add">+</button>
<div id="side" hidden><div class="bg" data-act="menu"></div><nav><h1>Library</h1><button data-act="nav" data-v="lib">Book Library</button><button data-act="nav" data-v="cats">Book Categories</button><button data-act="nav" data-v="notes">Notes</button><button data-act="export">Export backup</button><button data-act="import">Import backup</button><input id="imp" type="file" accept="application/json,.json" hidden><div class="sp"></div><div id="stat" class="s"></div><button class="ghost" data-act="signout">Sign out</button></nav></div>
<div id="npage" hidden></div><div id="sheet" hidden></div>
</div><div id="toast" hidden></div>
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2.45.4/dist/umd/supabase.js"></script>
<script>
const sb=supabase.createClient('https://guijyqkagbdascdxsoym.supabase.co','sb_publishable_51mTib40-xLq16tjLFUSFg_IVj0RRGn');
const T=['categories','books','reading_records','notes'],SL={not_started:'Not Started',in_progress:'In Progress',read:'Read'};
const $=s=>document.querySelector(s),uid=()=>crypto.randomUUID(),now=()=>new Date().toISOString();
const esc=s=>String(s??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
let S={},user=null,sy,syncing=false,V={view:'lib',lt:'plan',ct:'cat',nf:'all',year:new Date().getFullYear(),q:''};
const idb=new Promise((ok,no)=>{const r=indexedDB.open('booklib',1);r.onupgradeneeded=()=>[...T,'meta'].forEach(t=>r.result.createObjectStore(t,{keyPath:t=='meta'?'k':'id'}));r.onsuccess=()=>ok(r.result);r.onerror=()=>no(r.error)});
const tx=async(st,mode,fn)=>{const d=await idb;return new Promise((ok,no)=>{const t=d.transaction(st,mode),q=fn(t.objectStore(st));t.oncomplete=()=>ok(q&&q.result);t.onerror=()=>no(t.error)})};
const putRow=(t,r)=>tx(t,'readwrite',s=>s.put(r));
const live=t=>S[t].filter(r=>!r.deleted_at),bookById=id=>S.books.find(b=>b.id==id),catName=id=>S.categories.find(c=>c.id==id)?.name||'Uncategorized';
const toast=m=>{const e=$('#toast');e.textContent=m;e.hidden=false;clearTimeout(e.t);e.t=setTimeout(()=>e.hidden=true,2600)};
const setStat=m=>$('#stat').textContent=m;
async function load(){for(const t of T)S[t]=await tx(t,'readonly',s=>s.getAll())}
function save(t,row){row.updated_at=now();row._dirty=1;S[t]=S[t].filter(x=>x.id!=row.id).concat(row);putRow(t,row);render();clearTimeout(sy);sy=setTimeout(sync,400)}
async function sync(){
 if(syncing||!user)return;
 if(!navigator.onLine){setStat('Offline. Changes are saved on this device.');return}
 syncing=true;setStat('Syncing…');
 try{
  for(const t of T){const dirty=S[t].filter(r=>r._dirty);if(!dirty.length)continue;
   const {error}=await sb.from(t).upsert(dirty.map(({_dirty,...r})=>({...r,user_id:user.id})));if(error)throw error;
   for(const r of dirty)if(S[t].find(x=>x.id==r.id)===r){delete r._dirty;await putRow(t,r)}}
  const cur=(await tx('meta','readonly',s=>s.get('cur')))?.v||{};
  for(const t of T){let since=cur[t]||'1970-01-01T00:00:00Z';
   for(;;){const {data,error}=await sb.from(t).select('*').gt('updated_at',since).order('updated_at').limit(1000);if(error)throw error;if(!data.length)break;
    for(const r of data){const l=S[t].find(x=>x.id==r.id);if(l&&l._dirty)continue;S[t]=S[t].filter(x=>x.id!=r.id).concat(r);await putRow(t,r)}
    since=data[data.length-1].updated_at;if(data.length<1000)break}
   cur[t]=since}
  await tx('meta','readwrite',s=>s.put({k:'cur',v:cur}));
  setStat('Synced '+new Date().toLocaleTimeString([],{hour:'2-digit',minute:'2-digit'}));render();
 }catch(e){setStat('Sync failed. Will retry. '+(e.message||''))}
 syncing=false}
const recs=()=>live('reading_records').map(r=>({r,b:bookById(r.book_id)})).filter(i=>i.b&&!i.b.deleted_at);
const bestRec=id=>live('reading_records').filter(r=>r.book_id==id).sort((a,b)=>(b.year||0)-(a.year||0))[0];
const bookRow=(b,r)=>`<li class="row" data-act="book" data-id="${b.id}"><div><div class="t" dir="auto">${esc(b.title)}</div>${b.author?`<div class="s" dir="auto">${esc(b.author)}</div>`:''}</div><div class="m">${r?`<span class="pill ${r.status}">${SL[r.status]}</span>`:''}${b.total_pages?`<span>${b.total_pages} pages</span>`:''}</div></li>`;
function groups(items){const m={};items.forEach(i=>(m[catName(i.b.category_id)]??=[]).push(i));
 return Object.keys(m).sort().map(k=>`<h3>${esc(k)}</h3><ul>${m[k].sort((a,b)=>a.b.title.localeCompare(b.b.title)).map(i=>bookRow(i.b,i.r)).join('')}</ul>`).join('')||'<p class="empty">No books here yet. Tap + to add one.</p>'}
const tabs=(a,cur,act)=>`<div class="tabs">${a.map(([k,l])=>`<button data-act="${act}" data-v="${k}" class="${k==cur?'on':''}">${l}</button>`).join('')}</div>`;
function vLib(){const R=recs(),ip=R.filter(i=>i.r.status=='in_progress'),h=(ip.length?`<h3>Continue</h3><ul>${ip.map(i=>bookRow(i.b,i.r)).join('')}</ul>`:'')+tabs([['plan','Reading plan'],['want','Want to read']],V.lt,'lt');
 if(V.lt=='want')return h+groups(R.filter(i=>i.r.year==null));
 return h+`<div class="yr"><button data-act="yr" data-d="-1" aria-label="Previous year">‹</button><b>${V.year}</b><button data-act="yr" data-d="1" aria-label="Next year">›</button></div>`+groups(R.filter(i=>i.r.year==V.year))}
function vCats(){const h=tabs([['cat','By category'],['year','By year']],V.ct,'ct');
 if(V.ct=='cat')return h+groups(live('books').map(b=>({b,r:bestRec(b.id)})));
 const R=recs(),ys=[...new Set(R.map(i=>i.r.year))].sort((a,b)=>(b||0)-(a||0));
 return h+(ys.map((y,i)=>`<details ${i==0?'open':''}><summary>${y??'Want to read'}</summary>${groups(R.filter(x=>x.r.year==y))}</details>`).join('')||'<p class="empty">No reading records yet.</p>')}
const noteRow=n=>{const bk=n.book_id?bookById(n.book_id)?.title:n.book_text,meta=[new Date(n.created_at).toLocaleDateString(),n.category_id&&catName(n.category_id),bk&&bk+(n.page?' p. '+n.page:'')].filter(Boolean).join(' / ');
 return `<li class="row" data-act="note" data-id="${n.id}"><div><div class="t" dir="auto">${esc(n.title||'Untitled')}</div><div class="sn" dir="auto">${esc(n.content.split('\n').find(l=>l.trim())||'')}</div><div class="m2" dir="auto">${esc(meta)}</div></div></li>`};
function vNotes(){const f=V.nf,N=live('notes').filter(n=>f=='all'||(f[0]=='c'?n.category_id==f.slice(2):n.book_id==f.slice(2))).sort((a,b)=>b.created_at.localeCompare(a.created_at));
 const op=(v,l)=>`<option value="${v}" ${f==v?'selected':''}>${esc(l)}</option>`,bks=live('books').filter(b=>live('notes').some(n=>n.book_id==b.id));
 return `<select class="flt" data-act="nf"><option value="all">All notes</option><optgroup label="Category">${live('categories').map(c=>op('c:'+c.id,c.name)).join('')}</optgroup><optgroup label="Book">${bks.map(b=>op('b:'+b.id,b.title)).join('')}</optgroup></select><ul>${N.map(noteRow).join('')||'<li class="empty">No notes yet. Tap + to add one.</li>'}</ul>`}
function search(q){const B=live('books').filter(b=>(b.title+' '+(b.author||'')).toLowerCase().includes(q)).map(b=>bookRow(b,bestRec(b.id))),N=live('notes').filter(n=>((n.title||'')+' '+n.content).toLowerCase().includes(q)).map(noteRow);
 return `<h3>Books</h3><ul>${B.join('')||'<li class="empty">No books found</li>'}</ul><h3>Notes</h3><ul>${N.join('')||'<li class="empty">No notes found</li>'}</ul>`}
function render(){const q=V.q.trim().toLowerCase();$('#title').textContent={lib:'Book Library',cats:'Book Categories',notes:'Notes'}[V.view];
 $('#main').innerHTML=q?search(q):{lib:vLib,cats:vCats,notes:vNotes}[V.view]()}
const sheet=h=>{$('#sheet').innerHTML=`<div class="bg" data-act="close"></div><div class="card">${h}</div>`;$('#sheet').hidden=false};
const closeSheet=()=>{$('#sheet').hidden=true;$('#sheet').innerHTML=''};
const catOpts=sel=>`<option value="">None</option>${live('categories').sort((a,b)=>a.name.localeCompare(b.name)).map(c=>`<option value="${c.id}" ${c.id==sel?'selected':''}>${esc(c.name)}</option>`).join('')}<option value="__new">+ New category…</option>`;
const statusOpts=sel=>Object.entries(SL).map(([k,v])=>`<option value="${k}" ${k==sel?'selected':''}>${v}</option>`).join('');
const recBlock=id=>live('reading_records').filter(r=>r.book_id==id).sort((a,b)=>(b.year||0)-(a.year||0)).map(r=>`<div class="rr"><input type="number" inputmode="numeric" data-rec="${r.id}" data-f="year" placeholder="No year" value="${r.year??''}"><select data-rec="${r.id}" data-f="status">${statusOpts(r.status)}</select><button class="x" data-act="rec-del" data-id="${r.id}" aria-label="Remove">✕</button></div>`).join('')||'<p class="s">No reading records.</p>';
const bar=(id,del,saveAct)=>`<div class="bar">${id?`<button class="danger" data-act="${del}" data-id="${id}">Delete</button>`:''}<button class="ghost" data-act="close">Cancel</button><button class="pri" data-act="${saveAct}" data-id="${id||''}">Save</button></div>`;
function bookForm(id){const b=id&&bookById(id);
 sheet(`<h2>${b?'Edit book':'Add book'}</h2><label>Book title<input id="f_t" dir="auto" value="${esc(b?.title)}"></label><label>Author (optional)<input id="f_a" dir="auto" value="${esc(b?.author)}"></label><label>Category<select id="f_c" data-cat>${catOpts(b?.category_id)}</select></label><label>Total pages (optional)<input id="f_p" type="number" inputmode="numeric" min="1" value="${b?.total_pages||''}"></label>`+
 (b?`<h3>Reading history</h3><div id="recs">${recBlock(id)}</div><button class="ghost" data-act="rec-add" data-id="${id}">Add reading year</button><p class="s">${live('notes').filter(n=>n.book_id==id).length} linked notes</p>`
 :`<label>Reading status<select id="f_s">${statusOpts('not_started')}</select></label><label>Reading year (empty = Want to read)<input id="f_y" type="number" inputmode="numeric" value="${V.view=='lib'&&V.lt=='want'?'':V.year}"></label>`)+bar(id,'del-book','save-book'))}
function noteForm(id){const n=id&&S.notes.find(x=>x.id==id);
 sheet(`<h2>${n?'Edit note':'Add note'}</h2><label>Title (optional)<input id="n_t" dir="auto" value="${esc(n?.title)}"></label><label>Content<textarea id="n_c" dir="auto" rows="9">${esc(n?.content)}</textarea></label><label>Category<select id="n_cat" data-cat>${catOpts(n?.category_id)}</select></label><label>Book<select id="n_b"><option value="">No book</option>${live('books').sort((a,b)=>a.title.localeCompare(b.title)).map(b=>`<option value="${b.id}" ${b.id==n?.book_id?'selected':''}>${esc(b.title)}</option>`).join('')}</select><input id="n_bt" dir="auto" placeholder="or type a book name" value="${esc(n?.book_text)}"></label><label>Page (optional)<input id="n_pg" dir="auto" value="${esc(n?.page)}"></label>`+bar(id,'del-note','save-note'))}
document.addEventListener('click',e=>{const el=e.target.closest('[data-act]');if(!el)return;const a=el.dataset.act,id=el.dataset.id,v=el.dataset.v;
 if(a=='menu')$('#side').hidden=!$('#side').hidden;
 else if(a=='nav'){V.view=v;V.q='';$('#q').value='';$('#side').hidden=true;render()}
 else if(a=='lt'){V.lt=v;render()}else if(a=='ct'){V.ct=v;render()}
 else if(a=='yr'){V.year+=+el.dataset.d;render()}
 else if(a=='add')V.view=='notes'?noteEditor():bookForm();
 else if(a=='book')bookForm(id);else if(a=='note')noteEditor(id);else if(a=='close')closeSheet();
 else if(a=='save-book'){const t=$('#f_t').value.trim();if(!t)return toast('Title is required');
  const base=id?bookById(id):{id:uid(),user_id:user.id,created_at:now()};
  save('books',{...base,title:t,author:$('#f_a').value.trim()||null,category_id:$('#f_c').value||null,total_pages:parseInt($('#f_p').value)||null});
  if(!id)save('reading_records',{id:uid(),user_id:user.id,book_id:base.id,year:parseInt($('#f_y').value)||null,status:$('#f_s').value,created_at:now()});closeSheet()}
 else if(a=='del-book'){const n=live('notes').filter(x=>x.book_id==id).length;
  if(!confirm(n?`This book has ${n} linked note(s). The notes will be kept. Delete the book?`:'Delete this book?'))return;
  live('reading_records').filter(r=>r.book_id==id).forEach(r=>save('reading_records',{...r,deleted_at:now()}));save('books',{...bookById(id),deleted_at:now()});closeSheet()}
 else if(a=='rec-add'){const y=new Date().getFullYear();if(live('reading_records').some(r=>r.book_id==id&&r.year==y))return toast('This book already has a record for '+y+'. Change its year first.');
  save('reading_records',{id:uid(),user_id:user.id,book_id:id,year:y,status:'not_started',created_at:now()});$('#recs').innerHTML=recBlock(id)}
 else if(a=='rec-del'){const r=S.reading_records.find(x=>x.id==id);save('reading_records',{...r,deleted_at:now()});$('#recs').innerHTML=recBlock(r.book_id)}
 else if(a=='save-note'){const t=$('#n_t').value.trim(),c=$('#n_c').value;if(!t&&!c.trim())return toast('Write a title or some content');
  const base=id?S.notes.find(x=>x.id==id):{id:uid(),user_id:user.id,created_at:now()},bk=$('#n_b').value||null;
  save('notes',{...base,title:t||null,content:c,category_id:$('#n_cat').value||null,book_id:bk,book_text:bk?null:$('#n_bt').value.trim()||null,page:$('#n_pg').value.trim()||null});closeSheet()}
 else if(a=='del-note'){if(!confirm('Delete this note?'))return;save('notes',{...S.notes.find(x=>x.id==id),deleted_at:now()});closeSheet()}
 else if(a=='signout')signOut();else if(a=='export')backup();else if(a=='n-back')noteBack();else if(a=='n-menu')noteMenu();else if(a=='n-del')noteDel();
 else if(a=='n-ok'){const bk=$('#n_b').value||null;closeSheet();noteSave({category_id:$('#n_cat').value||null,book_id:bk,book_text:bk?null:$('#n_bt').value.trim()||null,page:$('#n_pg').value.trim()||null})}else if(a=='import')$('#imp').click()});
document.addEventListener('change',async e=>{const s=e.target;
 if(s.dataset.act=='nf'){V.nf=s.value;render()}
 else if(s.dataset.cat!==undefined&&s.value=='__new'){const n=(prompt('New category name')||'').trim();if(!n){s.value='';return}
  let c=live('categories').find(c=>c.name.toLowerCase()==n.toLowerCase());if(!c){c={id:uid(),user_id:user.id,name:n,created_at:now()};save('categories',c)}s.innerHTML=catOpts(c.id)}
 else if(s.dataset.rec){const r=S.reading_records.find(x=>x.id==s.dataset.rec);let v=s.value;
  if(s.dataset.f=='year'){v=parseInt(v)||null;if(live('reading_records').some(x=>x.id!=r.id&&x.book_id==r.book_id&&x.year==v)){toast('This book already has a record for that year');$('#recs').innerHTML=recBlock(r.book_id);return}}
  save('reading_records',{...r,[s.dataset.f]:v})}});
$('#q').addEventListener('input',e=>{V.q=e.target.value;render()});
let NID=null,nt2;
const metaOf=n=>{const bk=n.book_id?bookById(n.book_id)?.title:n.book_text;return [n.category_id&&catName(n.category_id),bk&&bk+(n.page?' p. '+n.page:'')].filter(Boolean).join(' / ')};
function noteEditor(id){NID=id||null;const n=id&&S.notes.find(x=>x.id==id);
 $('#npage').innerHTML=`<div class="nb"><button data-act="n-back">‹ Back</button><button data-act="n-menu" aria-label="Note settings">⋯</button></div><div class="nw"><input id="nt" dir="auto" placeholder="Title" value="${esc(n?.title)}"><div id="nm" dir="auto">${n?esc(metaOf(n)):''}</div><textarea id="nc" dir="auto" placeholder="Write here…">${esc(n?.content)}</textarea></div>`;
 $('#npage').hidden=false;if(!n)$('#nc').focus()}
function noteSave(extra){clearTimeout(nt2);if($('#npage').hidden)return;const t=$('#nt').value.trim(),c=$('#nc').value;let n=NID&&S.notes.find(x=>x.id==NID);
 if(!n){if(!t&&!c.trim()&&!extra)return;n={id:uid(),user_id:user.id,created_at:now(),content:''};NID=n.id}
 if(n.title==(t||null)&&n.content==c&&!extra)return;
 const row={...n,title:t||null,content:c,...extra};save('notes',row);$('#nm').textContent=metaOf(row)}
function noteClose(){$('#npage').hidden=true;$('#npage').innerHTML='';NID=null}
function noteBack(){noteSave();noteClose()}
function noteDel(){if(!confirm('Delete this note?'))return;clearTimeout(nt2);const n=S.notes.find(x=>x.id==NID);if(n)save('notes',{...n,deleted_at:now()});closeSheet();noteClose()}
function noteMenu(){noteSave();const n=(NID&&S.notes.find(x=>x.id==NID))||{};
 sheet(`<h2>Note settings</h2><label>Category<select id="n_cat" data-cat>${catOpts(n.category_id)}</select></label><label>Quoted from book<select id="n_b"><option value="">No book</option>${live('books').sort((a,b)=>a.title.localeCompare(b.title)).map(b=>`<option value="${b.id}" ${b.id==n.book_id?'selected':''}>${esc(b.title)}</option>`).join('')}</select><input id="n_bt" dir="auto" placeholder="or type a book name" value="${esc(n.book_text)}"></label><label>Page (optional)<input id="n_pg" dir="auto" value="${esc(n.page)}"></label><div class="bar">${n.id?'<button class="danger" data-act="n-del">Delete note</button>':''}<button class="pri" data-act="n-ok">Done</button></div>`)}
document.addEventListener('input',e=>{if(e.target.id=='nt'||e.target.id=='nc'){clearTimeout(nt2);nt2=setTimeout(noteSave,600)}});
addEventListener('pagehide',()=>noteSave());document.addEventListener('visibilitychange',()=>{if(document.hidden)noteSave()});
function backup(){const o={format:'booklib-backup',version:1,exported_at:now()};T.forEach(t=>o[t]=S[t].map(({_dirty,...r})=>r));
 const a=document.createElement('a');a.href=URL.createObjectURL(new Blob([JSON.stringify(o)],{type:'application/json'}));a.download='booklib-backup-'+now().slice(0,10)+'.json';a.click();toast('Backup exported')}
async function restore(f){let o;try{o=JSON.parse(await f.text())}catch(e){return toast('Not a valid backup file')}
 if(o?.format!='booklib-backup'||o.version!=1||T.some(t=>!Array.isArray(o[t])))return toast('Not a valid backup file');
 const ids=new Set(T.flatMap(t=>[...o[t],...S[t]].map(r=>r.id)));
 const bad=T.some(t=>o[t].some(r=>typeof r.id!='string'||(t=='books'&&(typeof r.title!='string'||(r.category_id&&!ids.has(r.category_id))))||(t=='reading_records'&&!ids.has(r.book_id))||(t=='notes'&&((r.category_id&&!ids.has(r.category_id))||(r.book_id&&!ids.has(r.book_id))))));
 if(bad)return toast('Backup is damaged. Nothing was imported.');
 const add=T.map(t=>o[t].filter(r=>!S[t].some(x=>x.id==r.id))),n=add.reduce((a,x)=>a+x.length,0),total=T.reduce((a,t)=>a+o[t].length,0);
 if(!n)return toast('Nothing new: everything in this backup is already here');
 if(!confirm(`This backup has ${total} items. ${n} are new and will be added. ${total-n} already exist and will be left untouched. Continue?`))return;
 for(const [i,t] of T.entries())for(const r of add[i]){const row={...r,user_id:user.id,_dirty:1};S[t].push(row);await putRow(t,row)}
 render();sync();toast(n+' items restored')}
$('#imp').addEventListener('change',e=>{const f=e.target.files[0];e.target.value='';$('#side').hidden=true;if(f)restore(f)});
async function signOut(){const pending=T.some(t=>S[t].some(r=>r._dirty));
 if(pending&&!confirm('Some changes are not synced yet. Signing out will lose them. Sign out anyway?'))return;
 await sb.auth.signOut();for(const t of [...T,'meta'])await tx(t,'readwrite',s=>s.clear());location.reload()}
$('#lf').addEventListener('submit',async e=>{e.preventDefault();$('#err').textContent='';
 const {data,error}=await sb.auth.signInWithPassword({email:$('#em').value.trim(),password:$('#pw').value});
 if(error){$('#err').textContent=navigator.onLine?'Wrong email or password.':'You are offline. Sign in needs internet the first time.';return}
 user=data.user;start()});
function start(){$('#login').hidden=true;$('#app').hidden=false;render();sync();addEventListener('online',sync);addEventListener('focus',sync);setInterval(sync,60000)}
(async()=>{await load();let s=null;try{s=(await sb.auth.getSession()).data.session}catch(e){}
 if(s){user=s.user;start()}else $('#login').hidden=false;
 if('serviceWorker' in navigator)navigator.serviceWorker.register('sw.js')})();
</script></body></html>

```