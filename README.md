 <h3> EventBus (Event Management System)</h3>
    <p>The EventBus allows <strong>loosely coupled communication</strong> between different components.</p>
    <p>First you need to download this one here as Dependency: https://github.com/berkcankarabulut/EventBusHandler</p>
    <ul>
        <li><strong>Action-based Events:</strong> Handles events without return values.</li>
        <li><strong>Func-based Events:</strong> Handles events with return values.</li>
        <li><strong>Key Methods:</strong></li>
        <ul>
            <li><code>Subscribe<T>(Action handler)</code> → Adds an event listener.</li>
            <li><code>Raise<T>()</code> → Triggers an event.</li>
            <li><code>RaiseWithResults<T, TResult>()</code> → Calls an event and returns results.</li>
            <li><code>ClearSubscriptions<T>()</code> → Clears all subscriptions.</li>
            <li><code>GetSubscriberCount<T>()</code> → Returns the number of subscribers.</li>
        </ul>
    </ul>
    <pre><code>void OnGameStart() { Debug.Log("Game Started!"); }
EventBus.Instance.Subscribe<GameStartEvent>(OnGameStart);
EventBus.Instance.Raise<GameStartEvent>();
EventBus.Instance.Unsubscribe<GameStartEvent>(OnGameStart);
    </code></pre>
