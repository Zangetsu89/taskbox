<script>
  import PureTaskList from './PureTaskList.svelte';
  import { taskStore, AppStore } from '../store';
  function onPinTask(event) {
    taskStore.pinTask(event.detail.id);
  }
  function onArchiveTask(event) {
    taskStore.archiveTask(event.detail.id);
  }
  function onAppState(event) {
    AppStore.AppState(event.detail.id);
  }
</script>

<div>
  <PureTaskList
    tasks={$taskStore}
    on:onPinTask={onPinTask}
    on:onArchiveTask={onArchiveTask}
    on:onAppState={onAppState}
  />
</div>