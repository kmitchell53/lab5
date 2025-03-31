# lab5

Priority
package lab5sassignments;

public interface Priority {
    void setPriority(int priority);
    int getPriority();
}


task

package lab5sassignments;
public class Task implements Priority {
    private String description;
    private int priority;

    public Task(String description, int priority) {
        this.description = description;
        setPriority(priority); // Ensuring priority is within valid range
    }

    @Override
    public void setPriority(int priority) {
        if (priority >= 1 && priority <= 5) {
            this.priority = priority;
        } else {
            throw new IllegalArgumentException("Priority must be between 1 and 5.");
        }
    }

    @Override
    public int getPriority() {
        return priority;
    }

    @Override
    public String toString() {
        return String.format("%-20s priority: %d", description, priority);
    }
}



tasklist

package lab5sassignments;
import java.util.ArrayList;
import java.util.List;

public class TaskList {
    public static void main(String[] args) {
        List<Task> tasks = new ArrayList<>();
        tasks.add(new Task("Attend class", 1));
        tasks.add(new Task("Homework", 2));
        tasks.add(new Task("Exercise", 3));
        tasks.add(new Task("Eat breakfast", 4));
        tasks.add(new Task("Eat lunch", 5));

        System.out.println("Priority Task List\n------------------");
        for (Task task : tasks) {
            System.out.println(task);
        }
    }
}
