/* New Things Every Day — Day 115 */
/* Creates a project task summary */

function dailyLog115() {
    const tasks = [
        { title: "Update README", priority: "High", completed: true },
        { title: "Fix bug #42", priority: "High", completed: false },
        { title: "Write tests", priority: "Medium", completed: true },
        { title: "Refactor helpers", priority: "Low", completed: false },
        { title: "Review pull request", priority: "Medium", completed: true }
    ];

    const summary = tasks.reduce((result, task) => {
        if (!result[task.priority]) {
            result[task.priority] = {
                total: 0,
                completed: 0
            };
        }

        result[task.priority].total++;

        if (task.completed) {
            result[task.priority].completed++;
        }

        return result;
    }, {});

    console.log({
        day: 115,
        timestamp: new Date().toISOString(),
        priorities: summary,
        totalTasks: tasks.length
    });
}

dailyLog115();
