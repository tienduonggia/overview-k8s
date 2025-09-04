---
transition: fade-out
---

# Vertical & Horizontal Scaling
<div grid grid-cols-2 gap-2 h-75>

<v-clicks>

  <div border="2 solid black/5" rounded-lg overflow-hidden bg="black/5" backdrop-blur-sm h-full>
    <div flex items-center bg="white/10" backdrop-blur px-3 py-2 rounded-md>
      <div i-carbon:Fit-to-height text-amber-300 text-sm mr-2 />
      <div font-semibold>
          Vertical Scaling (Scale up)
      </div>
    </div>
    <div px-4 py-3>
      <div flex flex-col gap-3>
        <div>
          <div text-sm font-medium>Increase resources on a single server (CPU, RAM, Disk)</div>
          <div text-xs opacity-70>Expensive for high-end hardware</div>
        </div>
        <div>
          <div text-sm font-medium>Physical limits – can’t upgrade forever.</div>
        </div>
        <div>
          <div text-sm font-medium>Single point of failure</div>
        </div>
      </div>
    </div>
  </div>

  <div border="2 solid black/5" rounded-lg overflow-hidden bg="black/5" backdrop-blur-sm h-full>
    <div flex items-center bg="white/10" backdrop-blur px-3 py-2 rounded-md>
      <div i-carbon:Fit-to-width text-amber-300 text-sm mr-2 />
      <div font-semibold>
        Horizontal Scaling (Scale width)
      </div>
    </div>
    <div px-4 py-3>
      <div flex flex-col gap-3>
        <ul>
          <li text-sm font-medium>Add more servers/nodes to distribute the load.</li>
          <li text-sm font-medium>Almost unlimited scalability.</li>
          <li text-sm font-medium>Better availability & fault tolerance (one node fails, others keep running).</li>
          <li text-sm font-medium>More complex management (networking, consistency, orchestration).</li>
        </ul>
      </div>
    </div>
  </div>

</v-clicks>

</div>